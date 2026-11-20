---
title: "Week 1 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Week 1 Objectives:

* **Topic:** AWS Fundamentals & IAM
* **Main Objective:** Understand basic AWS concepts and how access permissions are managed using IAM

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Day 1 | - **Plan:** AWS Basics <br> - **Main Task:** AWS Fundamentals <br> - **Detailed Activities:** Learned about the AWS Management Console, Regions, Availability Zones, and common AWS services | 15/09/2026 | 15/09/2026 | [AWS IAM Management Console](https://console.aws.amazon.com/iam/home?region=us-east-1) <br> [AWS Identity and Access Management (IAM) User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) |
| Day 2 | - **Plan:** User Management <br> - **Main Task:** IAM Users & Groups <br> - **Detailed Activities:** Learned how to create IAM Users, User Groups, and assign permissions | 17/09/2026 | 17/09/2026 | [AWS IAM Management Console](https://console.aws.amazon.com/iam/home?region=us-east-1) <br> [AWS Identity and Access Management (IAM) User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) |
| Day 3 | - **Plan:** Access Control <br> - **Main Task:** IAM Roles & Policies <br> - **Detailed Activities:** Learned about IAM Roles, Policies, and the Principle of Least Privilege | 20/09/2026 | 20/09/2026 | [AWS IAM Management Console](https://console.aws.amazon.com/iam/home?region=us-east-1) <br> [AWS Identity and Access Management (IAM) User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) |

### Week 1 Achievements:

* **AWS Global Infrastructure:** How AWS organizes services across Regions and Availability Zones for high availability and fault isolation
* **IAM Identities & Policies:** Managing access through IAM Users, User Groups, temporary IAM Roles, and JSON permission policies
* **Account Security Baseline:** Securing the Root Account, enforcing Multi-Factor Authentication (MFA), and applying Least Privilege

The first week helped me understand how AWS global infrastructure is organized and why identity management is the first line of defense in the cloud. Rather than sharing root credentials or granting broad access, AWS IAM separates human users, groups, and temporary service roles so every identity receives only the exact permissions required for its task.

Key takeaways:

- **Infrastructure Layout:** Regions and Availability Zones isolate failures and keep applications close to users.
- **Role-Based Access:** Grouping users and using IAM Roles for services is much safer and easier to maintain than attaching policies to individual users.
- **Root & Least Privilege:** The Root Account should be locked down with MFA for administrative emergencies only, while daily work runs on least-privilege IAM identities.
