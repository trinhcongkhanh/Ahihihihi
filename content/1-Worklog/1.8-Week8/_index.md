---
title: "Week 8 Worklog"
date: 2024-01-01
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* **Topic:** Infrastructure as Code (IaC)
* **Main Objective:** Understand what IaC is and how to create AWS resources from code instead of clicking in the console, mainly with AWS CloudFormation

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Day 1 | - **Plan:** IaC Basics <br> - **Main Task:** Introduction to IaC <br> - **Detailed Activities:** Learned what IaC means and why teams use it instead of creating resources by hand. Read about common tools: AWS CloudFormation, AWS CDK and Terraform | 29/10/2026 | 29/10/2026 | [AWS CloudFormation User Guide](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html) <br> [AWS CDK Developer Guide](https://docs.aws.amazon.com/cdk/v2/guide/home.html) |
| Day 2 | - **Plan:** CloudFormation <br> - **Main Task:** Writing a First Template <br> - **Detailed Activities:** Learned the basic parts of a CloudFormation template in YAML: `Parameters`, `Resources` and `Outputs`. Wrote a small template to create an S3 bucket | 31/10/2026 | 31/10/2026 | [AWS CloudFormation User Guide](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html) <br> [AWS CDK Developer Guide](https://docs.aws.amazon.com/cdk/v2/guide/home.html) |
| Day 3 | - **Plan:** Stacks <br> - **Main Task:** Create, Update & Delete a Stack <br> - **Detailed Activities:** Deployed the template as a stack in the console. Changed the template and updated the stack, then deleted it and saw all resources removed together | 01/11/2026 | 01/11/2026 | [AWS CloudFormation User Guide](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html) <br> [AWS CDK Developer Guide](https://docs.aws.amazon.com/cdk/v2/guide/home.html) |
| Day 4 | - **Plan:** Practice <br> - **Main Task:** A Bigger Template <br> - **Detailed Activities:** Wrote a template that creates an EC2 instance with a security group. Used a parameter for the instance type so the same template can be reused | 02/11/2026 | 02/11/2026 | [AWS CloudFormation User Guide](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html) <br> [AWS CDK Developer Guide](https://docs.aws.amazon.com/cdk/v2/guide/home.html) |
| Day 5 | - **Plan:** Review <br> - **Main Task:** Other Tools & Good Habits <br> - **Detailed Activities:** Looked at short examples of AWS CDK and Terraform to compare with CloudFormation. Put my templates in a Git repository to keep track of changes | 04/11/2026 | 04/11/2026 | [AWS CloudFormation User Guide](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html) <br> [AWS CDK Developer Guide](https://docs.aws.amazon.com/cdk/v2/guide/home.html) |

### Week 8 Achievements:

* **AWS CloudFormation:** Defining repeatable infrastructure in YAML templates (`Parameters`, `Resources`, `Outputs`) and managing resource lifecycles as Stacks
* **IaC Tooling Ecosystem:** Comparing AWS-native tools (CloudFormation, AWS CDK) with multi-cloud provisioning tools (Terraform)
* **IaC Best Practices:** Versioning templates in Git, parameterizing environment settings, never hard-coding secrets, and avoiding manual console drift

Moving from manual console clicks to **Infrastructure as Code (IaC)** completely changed how I build and clean up AWS environments. Instead of hoping I remember every step when recreating a setup, a CloudFormation YAML template serves as both the blueprint and the documentation of what is running—and deleting the stack removes every associated resource at once, leaving no forgotten instances or buckets behind.

Key takeaways:

- **Repeatable & Reusable:** Parameterized CloudFormation templates allow the exact same architecture to be deployed reliably across environments.
- **Clean Lifecycle Management:** Creating, updating, or deleting a stack manages all underlying resources as a single unit, preventing leftover costs.
- **Code Discipline for Infrastructure:** Templates belong in Git with zero hard-coded secrets, and resources created via IaC should never be modified manually in the console.
