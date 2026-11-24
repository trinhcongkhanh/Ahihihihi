---
title: "Week 3 Worklog"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* **Topic:** AWS Resource Access Manager (RAM)
* **Main Objective:** Learn how to share AWS resources between accounts without copying them or creating extra IAM users

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Day 1 | - **Plan:** RAM Overview <br> - **Main Task:** Introduction to AWS RAM <br> - **Detailed Activities:** Read about what RAM is and why it is used in multi-account setups. Learned the three parts of a resource share: resources, principals and permissions | 22/09/2026 | 22/09/2026 | [AWS Resource Access Manager (RAM) Console](https://console.aws.amazon.com/ram/home?region=us-east-1) <br> [AWS RAM User Guide](https://docs.aws.amazon.com/ram/latest/userguide/what-is.html) |
| Day 2 | - **Plan:** Sharing Resources <br> - **Main Task:** How a Resource Share Is Created <br> - **Detailed Activities:** Read about the steps to create a resource share in the console. Learned that a VPC subnet can only be shared with accounts in the same organization, while sharing other supported resources with an external account needs an invitation to be accepted | 23/09/2026 | 23/09/2026 | [AWS Resource Access Manager (RAM) Console](https://console.aws.amazon.com/ram/home?region=us-east-1) <br> [AWS RAM User Guide](https://docs.aws.amazon.com/ram/latest/userguide/what-is.html) |
| Day 3 | - **Plan:** RAM with Organizations <br> - **Main Task:** Sharing inside AWS Organizations <br> - **Detailed Activities:** Learned how to turn on sharing with AWS Organizations so accounts in the same organization don't need to accept invitations. Compared sharing to an OU vs. a single account | 24/09/2026 | 24/09/2026 | [AWS Resource Access Manager (RAM) Console](https://console.aws.amazon.com/ram/home?region=us-east-1) <br> [AWS RAM User Guide](https://docs.aws.amazon.com/ram/latest/userguide/what-is.html) |
| Day 4 | - **Plan:** Review <br> - **Main Task:** AWS CLI and security settings <br> - **Detailed Activities:** Read about basic `aws ram` commands. Looked at the "Allow external principals" option and how to limit sharing to the organization only | 25/09/2026 | 25/09/2026 | [AWS Resource Access Manager (RAM) Console](https://console.aws.amazon.com/ram/home?region=us-east-1) <br> [AWS RAM User Guide](https://docs.aws.amazon.com/ram/latest/userguide/what-is.html) |

### Week 3 Achievements:

* **Resource Shares (AWS RAM):** Sharing regional resources (VPC subnets, Transit Gateways, Route 53 rules) across accounts using resources, principals, and managed permissions
* **Organizations vs. External Sharing:** Seamless invitation-free sharing inside AWS Organizations/OUs vs. explicit invitation acceptance for external accounts
* **CLI & Boundary Security:** Understanding how the `aws ram` CLI manages shares and how to restrict external sharing with `ram:RequestedAllowsExternalPrincipals` SCP conditions

AWS RAM solves resource duplication in multi-account setups by letting one owner account share infrastructure directly with other accounts. Unlike cross-account IAM roles—where a user switches identity to access another account—RAM makes the shared resource (such as a VPC subnet) appear natively inside the recipient account so teams can launch EC2 instances into it while the owner account retains full control over the subnet itself.

Key takeaways:

- **Native Resource Sharing:** Shared resources can be used directly by recipient accounts without duplicating infrastructure or managing extra IAM users.
- **Owner Control Preserved:** Recipient accounts can use a shared resource within managed permissions, but only the owner account can modify or delete it.
- **Organization Guardrails:** Disabling external principals and enforcing SCP conditions prevents accidental resource sharing outside the organization.
