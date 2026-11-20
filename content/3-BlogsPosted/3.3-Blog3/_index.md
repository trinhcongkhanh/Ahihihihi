---
title: "Blog 3"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---
# RANSOMWARE DELETES THE BACKUPS TOO - HOW DO YOU KEEP A COPY NOBODY CAN DELETE?

<img src="../../images/blog3/post.png" alt="Proof of Post on AWS Study Group VN" width="700" style="border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;" />

**Link to the original post:** [AWS Study Group VN – Facebook](https://www.facebook.com/share/p/18z4csKQ1Z/)

The question is this: if an attacker already has admin rights, is there a backup that even the admin cannot delete? AWS Backup Vault Lock was designed to answer exactly that.

### 1. WHY DO YOU STILL LOSE DATA WHEN YOU HAVE BACKUPS?

Modern ransomware does not encrypt as soon as it gets in. Attackers usually stay hidden, escalate privileges, and cut off the victim's way back before triggering encryption. MITRE ATT&CK describes this step as technique T1490 (Inhibit System Recovery), alongside T1485 (Data Destruction) and T1486 (Data Encrypted for Impact).

In the cloud, this scenario is simpler than many people think. If backups live in the same account as the workload, a single access key with admin rights is enough to delete snapshots, delete recovery points, and delete the backup vault itself with a few API calls.

The core problem is that the right to delete backups and the right to administer the system belong to the same identity. When that identity is compromised, the original data and its copies are lost together. A ransomware-resistant backup strategy therefore has to meet three requirements: the copy cannot be deleted or altered (immutable), it sits apart from the production environment (isolated), and it has been checked as clean before restore (verified).

### 2. ARCHITECTURE AND MAIN COMPONENTS

The architecture uses three accounts in the same AWS Organization: a workload account running production, a backup account managed by the data protection team, and a recovery account used only during an incident. The diagram below numbers the six steps of this flow.

<img src="../../images/blog3/architecture.png" alt="Ransomware-resistant backup architecture with AWS Backup Vault Lock" width="900" style="border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;" />

Each service has its own role:

- **AWS Organizations:** applies service control policies (SCPs) and backup policies from the management account to every member account.
- **AWS Backup:** runs tag-based backup plans and creates recovery points for Amazon EC2, Amazon EBS, Amazon RDS, and Amazon S3.
- **Backup vault with Vault Lock:** holds the first copy inside the workload account, where nobody can delete it before the retention period ends.
- **Logically air-gapped vault:** holds the second copy in the backup account, locked automatically in compliance mode and encrypted by default with an AWS owned key.
- **Amazon GuardDuty Malware Protection for AWS Backup:** scans recovery points for malware after each backup.
- **Amazon EventBridge and Amazon SNS:** turn scan results into alerts for the security team.
- **AWS Resource Access Manager (RAM) and Multi-party approval:** share the vault with the recovery account when a restore is needed.

What stands out is that this architecture does not rely on a single layer of protection. Vault Lock prevents deletion, a separate account stops privileges from spreading, SCPs block destructive actions at the organization level, and GuardDuty answers which backup is still clean. Each layer is an independent boundary, so an attacker who gets past one is still stopped by another.

### 3. HOW DOES VAULT LOCK WORK?

AWS Backup Vault Lock applies the WORM (write once, read many) model to a backup vault. Once the vault is locked, AWS Backup rejects every request to delete a recovery point or change its lifecycle, even when the request comes from the root user.

Vault Lock has two modes. In governance mode, anyone with sufficient IAM permissions can still remove the lock, which makes it suitable for testing and for guarding against accidental deletion. In compliance mode, once the waiting period has passed, nobody can change or remove the lock, including the account owner and AWS itself.

That waiting period is called grace time, with a minimum of 3 days (72 hours). During it, the lock can still be modified or deleted. It is the last chance to catch a misconfiguration, because after that point everything becomes immutable.

Vault Lock also lets you set a minimum and maximum retention period. Backup or copy jobs whose retention falls outside that range fail. This stops an attacker from working around the lock by creating backups that live for one day and waiting for them to expire.

The following example creates a compliance mode lock with a 3-day grace time and retention between 7 and 35 days:

```bash
aws backup put-backup-vault-lock-configuration \
  --backup-vault-name prod-vault \
  --changeable-for-days 3 \
  --min-retention-days 7 \
  --max-retention-days 35
```

If you omit the `--changeable-for-days` parameter, the lock is created in governance mode.

### 4. ISOLATING BACKUPS AND DETECTING MALWARE BEFORE RESTORE

Immutability is only half the answer. If the only copy still sits in the compromised account, the attacker cannot delete it but can still obstruct recovery.

Recovery points are therefore copied to a logically air-gapped vault in the backup account. This type of vault is locked automatically with Vault Lock in compliance mode, is encrypted by default with an AWS owned key, and requires a minimum retention of 7 days. It can be shared through AWS RAM so another account can restore from it directly, without copying the data back.

At the organization level, SCPs block dangerous actions such as `backup:DeleteRecoveryPoint`, `backup:DeleteBackupVault`, and `backup:UpdateRecoveryPointLifecycle`. SCPs apply even to admins of member accounts, so credentials stolen in production are not enough to destroy the backups.

The remaining question is which backup is still clean. Ransomware can stay hidden for weeks, so the most recent backup may not be usable. Amazon GuardDuty Malware Protection for AWS Backup, launched on 19/11/2025, scans Amazon EC2, Amazon EBS, and Amazon S3 recovery points after each backup. The result is either `NO_THREATS_FOUND` or `THREATS_FOUND`, and it is also published as an event on Amazon EventBridge so alerts can be sent through Amazon SNS.

When recovery is needed, the operations team picks the most recent clean recovery point and restores it into the recovery account. Since 17/06/2025, logically air-gapped vaults also support Multi-party approval: a group of trusted people must approve together before the vault is shared, even when the account that owns the vault is no longer accessible.

### 5. GETTING STARTED

The architecture can be rolled out in six steps:

1. Create a dedicated backup account in AWS Organizations and enable cross-account backup from the management account.
2. Create a backup vault in the workload account and enable Vault Lock. Try governance mode first, then create the compliance mode lock.
3. Create a logically air-gapped vault in the backup account, then add it as a copy destination in the backup plan.
4. Attach SCPs that block backup deletion and modification actions to the member accounts.
5. Enable malware scanning in the backup plan, create an EventBridge rule for `THREATS_FOUND` results, and send them to the security team's SNS topic.
6. Share the vault with the recovery account through AWS RAM and run restore testing on a schedule.

### 6. LIMITATIONS TO CONSIDER

- **Compliance mode cannot be undone.** If retention is set too long, the organization pays for storage until it expires. Recovery points with “Always” retention are kept forever once grace time ends.
- **Vault Lock only controls operations that go through AWS Backup.** According to the AWS documentation, direct EC2 API calls such as `ec2:ModifySnapshotAttribute` can still share a snapshot externally, and `ec2:DisableImage` can block a restore. These actions need to be blocked separately with IAM policies or SCPs.
- **The lock does not protect a closed account.** If the account is not reopened within 90 days, AWS deletes the vault contents even with Vault Lock in place.
- **Immutable does not mean clean.** GuardDuty only reports scan results; it does not delete or block infected recovery points, and scanning is billed under GuardDuty. Incremental scans do not yet support EC2 recovery points stored in a logically air-gapped vault.
- **It does not stop data theft.** In double extortion, attackers threaten to publish the data rather than only encrypting it, and backups do not address that risk.
- **Cost and coverage.** Keeping two copies increases storage cost, and logically air-gapped vaults do not yet support every resource type or every Region. A backup that has never been test-restored cannot be considered trustworthy.

### 7. CONCLUSION

Having backups does not guarantee you can recover. What matters is that a copy exists beyond the reach of the very identities that can be compromised.

AWS Backup Vault Lock, combined with a logically air-gapped vault, SCPs, and GuardDuty Malware Protection, is an approach worth considering for organizations running critical workloads on AWS, especially in finance, securities, and e-commerce.

Its real-world effectiveness, however, depends on how accounts are separated, how retention is designed, and how regularly restores are rehearsed.

Fighting ransomware is not only about keeping attackers out. It is also about making sure that when every other layer of defense fails, the organization still has a clean copy to go back to.

**References:**
- [AWS Backup Developer Guide – AWS Backup Vault Lock](https://docs.aws.amazon.com/aws-backup/latest/devguide/vault-lock.html)
- [AWS Backup Developer Guide – Logically air-gapped vault](https://docs.aws.amazon.com/aws-backup/latest/devguide/logicallyairgappedvault.html)
- [AWS Storage Blog – Securing backup data against modern threats with AWS Backup](https://aws.amazon.com/blogs/storage/securing-backup-data-against-modern-threats-with-aws-backup/)
