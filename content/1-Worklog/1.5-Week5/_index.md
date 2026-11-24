---
title: "Week 5 Worklog"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* **Topic:** Amazon GuardDuty & Amazon Inspector
* **Main Objective:** Learn how AWS detects suspicious activity in an account with GuardDuty, and how Inspector finds software vulnerabilities in EC2 instances, container images and Lambda functions

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Day 1 | - **Plan:** GuardDuty Basics <br> - **Main Task:** Introduction to GuardDuty <br> - **Detailed Activities:** Read about what GuardDuty does and which data it looks at: CloudTrail events, VPC Flow Logs and DNS logs. Turned on GuardDuty in my lab account and was surprised I didn't have to set up those logs myself | 05/10/2026 | 05/10/2026 | [Amazon GuardDuty User Guide](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html) <br> [Amazon Inspector User Guide](https://docs.aws.amazon.com/inspector/latest/user/what-is-inspector.html) |
| Day 2 | - **Plan:** Findings <br> - **Main Task:** Reading GuardDuty Findings <br> - **Detailed Activities:** Generated sample findings and went through a few of them, like `UnauthorizedAccess:EC2/SSHBruteForce` and `Recon:EC2/PortProbeUnprotectedPort`. Learned how to read the finding name, severity and the affected resource | 06/10/2026 | 06/10/2026 | [Amazon GuardDuty User Guide](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html) <br> [Amazon Inspector User Guide](https://docs.aws.amazon.com/inspector/latest/user/what-is-inspector.html) |
| Day 3 | - **Plan:** Alerts & Tuning <br> - **Main Task:** EventBridge Alerts and Suppression Rules <br> - **Detailed Activities:** Created an EventBridge rule that sends high-severity findings to my email through SNS. Looked at suppression rules and trusted IP lists to cut down noise from known activity | 07/10/2026 | 07/10/2026 | [Amazon GuardDuty User Guide](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html) <br> [Amazon Inspector User Guide](https://docs.aws.amazon.com/inspector/latest/user/what-is-inspector.html) |
| Day 4 | - **Plan:** Inspector Basics <br> - **Main Task:** Introduction to Amazon Inspector <br> - **Detailed Activities:** Activated Inspector and learned what it scans: EC2 instances, ECR container images and Lambda functions. Launched an old EC2 instance on purpose to see what vulnerabilities it would find | 08/10/2026 | 08/10/2026 | [Amazon GuardDuty User Guide](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html) <br> [Amazon Inspector User Guide](https://docs.aws.amazon.com/inspector/latest/user/what-is-inspector.html) |
| Day 5 | - **Plan:** Vulnerability Review <br> - **Main Task:** Inspector Findings & Comparison <br> - **Detailed Activities:** Went through the CVE findings, the Inspector risk score and the fix suggestions. Updated the packages on the instance and checked that the findings were closed. Compared GuardDuty and Inspector side by side | 09/10/2026 | 09/10/2026 | [Amazon GuardDuty User Guide](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html) <br> [Amazon Inspector User Guide](https://docs.aws.amazon.com/inspector/latest/user/what-is-inspector.html) |

### Week 5 Achievements:

* **Amazon GuardDuty:** Agentless threat detection across CloudTrail, VPC Flow Logs, and DNS logs (plus optional S3, EKS, RDS, and Lambda protection)
* **Alerting & Signal Tuning:** Routing high-severity findings to email via EventBridge + SNS and filtering false positives with suppression rules
* **Amazon Inspector:** Automated CVE and network exposure scanning across EC2, ECR images, and Lambda functions with risk-based prioritization
* **GuardDuty vs. Inspector:** GuardDuty detects active attacks happening now; Inspector identifies software weaknesses before they are exploited

While both services strengthen cloud security, they solve two different sides of the problem: **Inspector checks whether the door is unlocked, and GuardDuty warns when someone is trying to break in.** Scanning an outdated EC2 instance with Inspector showed me how quickly unpatched packages accumulate CVEs—and watching those findings close automatically after updating the packages made continuous vulnerability scanning and automated EventBridge alerting feel practical.

Key takeaways:

- **Proactive vs. Reactive Detection:** Inspector finds software CVEs before an attack occurs, while GuardDuty spots live threats like SSH brute-force or port probing in real time.
- **Zero-Agent Visibility:** GuardDuty analyzes CloudTrail, VPC Flow Logs, and DNS logs directly without requiring manual log setup.
- **Automated Incident Response:** Pairing GuardDuty and Inspector with EventBridge and SNS ensures critical findings reach engineers immediately without manual console checks.
