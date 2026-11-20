---
title: "Week 7 Worklog"
date: 2024-01-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

* **Topic:** Amazon VPC, Amazon CloudFront & Amazon API Gateway
* **Main Objective:** Understand how a private network is set up on AWS, how content is delivered faster to users, and how an API is exposed to the internet

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Day 1 | - **Plan:** VPC Basics <br> - **Main Task:** Introduction to Amazon VPC <br> - **Detailed Activities:** Learned what a VPC is and how it is split into public and private subnets. Created a simple VPC with one public and one private subnet | 23/10/2026 | 23/10/2026 | [Amazon VPC User Guide](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) <br> [Amazon CloudFront Developer Guide](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| Day 2 | - **Plan:** VPC Networking <br> - **Main Task:** Internet Gateway & Route Tables <br> - **Detailed Activities:** Added an Internet Gateway and a route table so the public subnet could reach the internet. Launched an EC2 instance in each subnet to see the difference | 24/10/2026 | 24/10/2026 | [Amazon VPC User Guide](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) <br> [Amazon CloudFront Developer Guide](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| Day 3 | - **Plan:** CloudFront <br> - **Main Task:** Introduction to Amazon CloudFront <br> - **Detailed Activities:** Learned what a CDN is and how edge locations cache content closer to users. Put a CloudFront distribution in front of an S3 bucket hosting a small static website | 25/10/2026 | 25/10/2026 | [Amazon VPC User Guide](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) <br> [Amazon CloudFront Developer Guide](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| Day 4 | - **Plan:** API Gateway <br> - **Main Task:** Introduction to Amazon API Gateway <br> - **Detailed Activities:** Created a simple API with a `GET` route and connected it to a Lambda function. Deployed it to a stage and called it from the browser | 27/10/2026 | 27/10/2026 | [Amazon VPC User Guide](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) <br> [Amazon CloudFront Developer Guide](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| Day 5 | - **Plan:** Review <br> - **Main Task:** Putting It Together <br> - **Detailed Activities:** Reviewed how the three services fit in one web app: CloudFront for the website, API Gateway for the backend, VPC for private resources. Deleted the resources after the lab | 28/10/2026 | 28/10/2026 | [Amazon VPC User Guide](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) <br> [Amazon CloudFront Developer Guide](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |

### Week 7 Achievements:

* **Amazon VPC & Subnets:** Designing isolated virtual networks with Public Subnets (routed via Internet Gateway) and Private Subnets for internal workloads
* **Amazon CloudFront (CDN):** Caching static website content at global Edge Locations with built-in HTTPS to reduce latency for end users
* **Amazon API Gateway:** Exposing backend services like Lambda through managed HTTP/REST routes (`GET`, `POST`) and deployment stages

This week connected the full network path of a modern AWS web application from the user's browser to the private backend. Thinking of **VPC** like a house made the networking pieces click: the VPC is the house, subnets are the rooms, and the Internet Gateway is the front door—only rooms with a route to the front door can talk to the internet, while sensitive resources stay protected in private rooms. On the public edge, **CloudFront** serves website assets from nearby edge locations, and **API Gateway** acts as a clean front door for backend Lambda functions.

Key takeaways:

- **Public vs. Private Isolation:** Web-facing components use public subnets with an Internet Gateway route, while databases and internal services stay isolated in private subnets.
- **Fast Content Delivery:** CloudFront caches static S3 content at edge locations worldwide so users load pages faster over HTTPS.
- **Managed API Front Door:** API Gateway handles public request routing and stages without exposing backend compute directly.
