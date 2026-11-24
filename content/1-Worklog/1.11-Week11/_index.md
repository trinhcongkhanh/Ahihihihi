---
title: "Week 11 Worklog"
date: 2024-01-01
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

* **Topic:** AWS Marketplace & AWS Billing Conductor
* **Main Objective:** Learn how to find and buy third-party software through AWS Marketplace, and how AWS Billing Conductor helps show custom costs to different teams or customers

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Day 1 | - **Plan:** Marketplace Basics <br> - **Main Task:** Introduction to AWS Marketplace <br> - **Detailed Activities:** Learned what AWS Marketplace is and what kinds of products it sells: AMIs, SaaS, containers and data products. Browsed a few security and monitoring tools | 16/11/2026 | 16/11/2026 | [AWS Marketplace Buyer Guide](https://docs.aws.amazon.com/marketplace/latest/buyerguide/what-is-marketplace.html) <br> [AWS Billing Conductor User Guide](https://docs.aws.amazon.com/billingconductor/latest/userguide/what-is-billingconductor.html) |
| Day 2 | - **Plan:** Pricing <br> - **Main Task:** Marketplace Pricing Models <br> - **Detailed Activities:** Compared pricing types like free, hourly, yearly and BYOL (Bring Your Own License). Launched a free AMI from Marketplace, then unsubscribed and terminated it after testing | 17/11/2026 | 17/11/2026 | [AWS Marketplace Buyer Guide](https://docs.aws.amazon.com/marketplace/latest/buyerguide/what-is-marketplace.html) <br> [AWS Billing Conductor User Guide](https://docs.aws.amazon.com/billingconductor/latest/userguide/what-is-billingconductor.html) |
| Day 3 | - **Plan:** Billing Conductor Basics <br> - **Main Task:** Introduction to AWS Billing Conductor <br> - **Detailed Activities:** Learned why Billing Conductor exists: to show each team or customer their own version of the bill without changing what AWS actually charges | 18/11/2026 | 18/11/2026 | [AWS Marketplace Buyer Guide](https://docs.aws.amazon.com/marketplace/latest/buyerguide/what-is-marketplace.html) <br> [AWS Billing Conductor User Guide](https://docs.aws.amazon.com/billingconductor/latest/userguide/what-is-billingconductor.html) |
| Day 4 | - **Plan:** Billing Setup <br> - **Main Task:** Billing Groups & Pricing Plans <br> - **Detailed Activities:** Learned how accounts are put into billing groups, how pricing plans add a markup or discount, and how custom line items add extra fees or credits | 19/11/2026 | 19/11/2026 | [AWS Marketplace Buyer Guide](https://docs.aws.amazon.com/marketplace/latest/buyerguide/what-is-marketplace.html) <br> [AWS Billing Conductor User Guide](https://docs.aws.amazon.com/billingconductor/latest/userguide/what-is-billingconductor.html) |
| Day 5 | - **Plan:** Review <br> - **Main Task:** Comparing and Summarizing <br> - **Detailed Activities:** Compared Billing Conductor with Cost Explorer and the normal AWS bill. Wrote down when each tool is useful | 20/11/2026 | 20/11/2026 | [AWS Marketplace Buyer Guide](https://docs.aws.amazon.com/marketplace/latest/buyerguide/what-is-marketplace.html) <br> [AWS Billing Conductor User Guide](https://docs.aws.amazon.com/billingconductor/latest/userguide/what-is-billingconductor.html) |

### Week 11 Achievements:

* **AWS Marketplace:** Procuring third-party software (AMIs, SaaS, containers) billed directly through AWS under Free, Hourly, Annual, or BYOL models
* **Subscription Governance:** Verifying vendors, restricting subscription permissions via IAM, and unsubscribing plus terminating test resources to prevent ongoing charges
* **AWS Billing Conductor:** Organizing accounts into Billing Groups and applying Pricing Plans (markups/discounts) and Custom Line Items for internal chargeback or reseller billing
* **Pro Forma Cost Views:** Understanding that Billing Conductor customizes what each billing group sees without altering the actual AWS invoice charged to the payer account

This week explored the commercial and financial side of cloud operations: procuring third-party tools through **AWS Marketplace** and customizing multi-account cost visibility with **AWS Billing Conductor**. Marketplace acts like an integrated app store where software subscriptions are consolidated onto the main AWS bill—making it critical to unsubscribe and terminate resources after testing. Meanwhile, Billing Conductor generates customized *pro forma* bills for specific teams or reseller customers using billing groups and pricing plans, without changing the actual amount AWS charges the management account.

Key takeaways:

- **Streamlined Software Procurement:** AWS Marketplace simplifies deploying third-party AMIs and SaaS using flexible pricing (including BYOL), but requires strict cleanup after trials.
- **Custom Chargeback & Showback:** Billing Groups, Pricing Plans, and Custom Line Items let organizations allocate tailored costs, fees, or credits to internal teams or clients.
- **Pro Forma vs. Actual Invoice:** Billing Conductor changes how costs are presented to each group, not what AWS bills the payer account.
