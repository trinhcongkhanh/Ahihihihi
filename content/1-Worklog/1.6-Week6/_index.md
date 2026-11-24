---
title: "Week 6 Worklog"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

* **Topic:** Amazon EC2, Amazon Lightsail & AWS Lambda
* **Main Objective:** Get a basic understanding of the three main ways to run code on AWS: virtual servers with EC2, simple servers with Lightsail, and serverless functions with Lambda, and know when to pick each one

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Day 1 | - **Plan:** EC2 Basics <br> - **Main Task:** Introduction to Amazon EC2 <br> - **Detailed Activities:** Learned the main parts of an EC2 instance: AMI, instance type, key pair, security group and EBS volume. Launched a `t3.micro` instance with Amazon Linux and connected to it with SSH | 12/10/2026 | 12/10/2026 | [Amazon EC2 User Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) <br> [AWS Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |
| Day 2 | - **Plan:** EC2 in Practice <br> - **Main Task:** Security Groups, User Data & Pricing <br> - **Detailed Activities:** Added inbound rules to the security group and used user data to install a web server when the instance starts. Read about the pricing options: On-Demand, Savings Plans, Reserved Instances and Spot. Stopped the instance at the end of the day so it wouldn't keep charging | 13/10/2026 | 13/10/2026 | [Amazon EC2 User Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) <br> [AWS Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |
| Day 3 | - **Plan:** Lightsail <br> - **Main Task:** Introduction to Amazon Lightsail <br> - **Detailed Activities:** Created a Lightsail instance from a WordPress blueprint. Attached a static IP and looked at the firewall and snapshot options. Noticed how much faster it was to set up compared to EC2 | 14/10/2026 | 14/10/2026 | [Amazon EC2 User Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) <br> [AWS Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |
| Day 4 | - **Plan:** Lambda Basics <br> - **Main Task:** Introduction to AWS Lambda <br> - **Detailed Activities:** Wrote a small Python function in the Lambda console and tested it with a test event. Learned about triggers, the execution role, timeout, memory settings and where to find the logs in CloudWatch | 15/10/2026 | 15/10/2026 | [Amazon EC2 User Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) <br> [AWS Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |
| Day 5 | - **Plan:** Review <br> - **Main Task:** Comparing EC2, Lightsail and Lambda <br> - **Detailed Activities:** Connected the Lambda function to an API Gateway endpoint and called it from the browser. Made a short comparison of the three services and cleaned up all the resources I created during the week | 16/10/2026 | 16/10/2026 | [Amazon EC2 User Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) <br> [AWS Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |

### Week 6 Achievements:

* **Amazon EC2 (IaaS):** Full OS control with AMIs, instance types, EBS storage, stateful Security Groups, and time-based pricing (On-Demand, Savings Plans, Spot)
* **Amazon Lightsail:** Bundled virtual servers with preconfigured blueprints (e.g., WordPress), static IPs, and predictable fixed monthly pricing
* **AWS Lambda (Serverless):** Event-driven functions (up to 15 minutes per run) billed per request and execution time, secured with least-privilege IAM Execution Roles
* **Compute Selection:** Choosing EC2 for full control, Lightsail for simple fixed-cost websites, and Lambda for short event-driven workloads

This week gave me a clear framework for choosing how to run code on AWS. **EC2** provides a full virtual machine where I control the OS and networking—but because it bills for every hour the server is running, unused instances must be stopped. **Lightsail** trades deep customization for speed and a fixed monthly bundle, while **Lambda** removes server management entirely so code only exists and costs money when triggered by an event such as an API Gateway request.

Key takeaways:

- **Control vs. Convenience:** Use EC2 when deep OS/network customization is required, and Lightsail when launching small apps or websites quickly.
- **Pay-for-Uptime vs. Pay-per-Execution:** EC2 charges while running even if idle, whereas Lambda bills strictly for request count and execution duration.
- **Compute Security:** Restrict EC2 SSH access to specific IPs in Security Groups, and grant Lambda functions minimal IAM Execution Roles.
