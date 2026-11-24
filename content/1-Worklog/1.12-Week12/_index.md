---
title: "Week 12 Worklog"
date: 2024-01-01
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Week 12 Objectives:

* **Topic:** AWS Key Management Service (KMS) & AWS CloudHSM
* **Main Objective:** Understand how AWS creates and protects encryption keys, and when to use the managed KMS service or a dedicated CloudHSM

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Day 1 | - **Plan:** KMS Basics <br> - **Main Task:** Introduction to AWS KMS <br> - **Detailed Activities:** Learned what KMS does and the three kinds of keys: AWS owned, AWS managed and customer managed. Created my first customer managed key | 23/11/2026 | 23/11/2026 | [AWS KMS Documentation](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html) <br> [AWS CloudHSM Documentation](https://docs.aws.amazon.com/cloudhsm/latest/userguide/introduction.html) |
| Day 2 | - **Plan:** Using Keys <br> - **Main Task:** Encrypting AWS Resources <br> - **Detailed Activities:** Turned on encryption for an S3 bucket and an EBS volume using my own KMS key. Learned the basic idea of envelope encryption: a data key locks the data, and the KMS key locks the data key | 24/11/2026 | 24/11/2026 | [AWS KMS Documentation](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html) <br> [AWS CloudHSM Documentation](https://docs.aws.amazon.com/cloudhsm/latest/userguide/introduction.html) |
| Day 3 | - **Plan:** Access Control <br> - **Main Task:** Key Policies & Rotation <br> - **Detailed Activities:** Edited the key policy so only certain users and roles can use the key. Turned on automatic key rotation and checked CloudTrail to see who used the key | 25/11/2026 | 25/11/2026 | [AWS KMS Documentation](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html) <br> [AWS CloudHSM Documentation](https://docs.aws.amazon.com/cloudhsm/latest/userguide/introduction.html) |
| Day 4 | - **Plan:** CloudHSM <br> - **Main Task:** Introduction to AWS CloudHSM <br> - **Detailed Activities:** Learned that CloudHSM gives a dedicated hardware security module that only my account controls. Read about clusters across Availability Zones and the HSM user roles | 26/11/2026 | 26/11/2026 | [AWS KMS Documentation](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html) <br> [AWS CloudHSM Documentation](https://docs.aws.amazon.com/cloudhsm/latest/userguide/introduction.html) |
| Day 5 | - **Plan:** Review <br> - **Main Task:** KMS vs. CloudHSM <br> - **Detailed Activities:** Compared the two services by control, cost and effort. Learned why it is better to disable a key or schedule deletion with a waiting period than to delete it right away | 27/11/2026 | 27/11/2026 | [AWS KMS Documentation](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html) <br> [AWS CloudHSM Documentation](https://docs.aws.amazon.com/cloudhsm/latest/userguide/introduction.html) |

### Week 12 Achievements:

* **AWS KMS:** KMS is a managed service for creating and controlling encryption keys. The keys stay inside KMS and are used to encrypt data in services like S3, EBS, RDS and Secrets Manager
* **Key Types:** AWS owned and AWS managed keys are handled by AWS. Customer managed keys give me control over the policy, rotation and deletion
* **Envelope Encryption:** Instead of sending large data to KMS, a small data key encrypts the data, and the KMS key encrypts that data key
* **Key Security:** Use key policies with least privilege, turn on automatic rotation, check key usage in CloudTrail, and use the waiting period before deleting a key
* **AWS CloudHSM:** CloudHSM is a dedicated, single-tenant hardware device in my VPC. I manage the keys and users myself, and AWS cannot see the keys
* **KMS vs. CloudHSM:** KMS is easier and cheaper for most cases. CloudHSM is for strict compliance rules or when a company needs full control of the hardware

For the last week, I studied something that sits under almost everything I learned before: encryption keys. S3, EBS, RDS and Secrets Manager all depend on them, but until now I had never looked at where the keys actually come from.

KMS turned out to be simpler than I expected. I create a key, decide who can use it, and AWS takes care of keeping it safe. Envelope encryption was the part that took me longest. Thinking of it as "a key inside a locked box" made it click: the data key opens the data, and the KMS key opens the box holding the data key.

CloudHSM felt like the opposite. It gives more control, but I also get more responsibility. If I lose the HSM credentials, nobody can recover the keys for me, not even AWS. That made it clear to me why most projects use KMS, and why CloudHSM is mainly for companies with strict security rules.

Key points learned:

- What KMS is and the three types of keys
- Encrypting S3 and EBS with a customer managed key
- The basic idea of envelope encryption
- Protecting keys with key policies, rotation and CloudTrail logs
- What CloudHSM is and how it is different from KMS
- Choosing between KMS and CloudHSM based on control, cost and compliance
