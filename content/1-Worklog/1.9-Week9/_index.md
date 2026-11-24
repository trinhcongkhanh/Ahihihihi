---
title: "Week 9 Worklog"
date: 2024-01-01
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* **Topic:** Amazon CloudWatch, AWS Auto Scaling, AWS CloudFormation & AWS Config
* **Main Objective:** Learn how to monitor resources, scale them automatically when traffic changes, deploy them with code, and keep track of their configuration

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Day 1 | - **Plan:** Monitoring <br> - **Main Task:** Introduction to CloudWatch <br> - **Detailed Activities:** Learned about metrics, logs, alarms and dashboards. Created an alarm that emails me when an EC2 instance's CPU goes above 70% | 02/11/2026 | 02/11/2026 | [Amazon CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) <br> [AWS Config Developer Guide](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html) |
| Day 2 | - **Plan:** Scaling <br> - **Main Task:** Introduction to Auto Scaling <br> - **Detailed Activities:** Created a launch template and an Auto Scaling group with a minimum, desired and maximum number of instances. Added a policy to keep average CPU around 50% | 03/11/2026 | 03/11/2026 | [Amazon CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) <br> [AWS Config Developer Guide](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html) |
| Day 3 | - **Plan:** Testing <br> - **Main Task:** Watching Auto Scaling Work <br> - **Detailed Activities:** Put load on an instance to push CPU up and watched new instances get added. Stopped one instance on purpose and saw Auto Scaling replace it | 04/11/2026 | 04/11/2026 | [Amazon CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) <br> [AWS Config Developer Guide](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html) |
| Day 4 | - **Plan:** Deploying <br> - **Main Task:** CloudFormation for the Setup <br> - **Detailed Activities:** Wrote a CloudFormation template for the Auto Scaling group and the CloudWatch alarm, so the whole setup can be created again with one stack | 05/11/2026 | 05/11/2026 | [Amazon CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) <br> [AWS Config Developer Guide](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html) |
| Day 5 | - **Plan:** Compliance <br> - **Main Task:** Introduction to AWS Config <br> - **Detailed Activities:** Turned on AWS Config and added a few managed rules, like checking that S3 buckets are not public and SSH is not open to everyone. Reviewed which resources were compliant and which were not | 06/11/2026 | 06/11/2026 | [Amazon CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) <br> [AWS Config Developer Guide](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html) |

### Week 9 Achievements:

* **Amazon CloudWatch:** Collecting resource metrics and logs, building dashboards, and configuring threshold alarms to send alerts or trigger scaling
* **AWS Auto Scaling:** Maintaining fleet health and capacity (min/desired/max) using Launch Templates and Target Tracking scaling policies
* **AWS Config:** Tracking resource configuration history and auditing compliance continuously against managed rules (e.g., public S3 or open SSH)
* **Integrated Operations:** Deploying CloudWatch + Auto Scaling via CloudFormation so monitoring, scaling, and compliance work together as one system

This week shifted my focus from building infrastructure to keeping it healthy and compliant in production. Stress-testing CPU load showed me why **CloudWatch** and **Auto Scaling** belong together: CloudWatch detects the spike, and Auto Scaling automatically adds or replaces EC2 instances without human intervention. Meanwhile, **AWS Config** acts as a continuous compliance checklist—rather than blocking changes, it records configuration history and flags resources that violate security rules so they can be remediated.

Key takeaways:

- **Detect & React Automatically:** CloudWatch alarms and Auto Scaling target-tracking policies keep capacity aligned with real-time load and replace unhealthy instances automatically.
- **Repeatable Operational Setup:** Packaging Auto Scaling groups and CloudWatch alarms into a single CloudFormation stack makes the entire resilient setup reproducible.
- **Continuous Configuration Auditing:** AWS Config evaluates resources against compliance rules over time, giving clear visibility into misconfigurations without replacing preventive controls.
