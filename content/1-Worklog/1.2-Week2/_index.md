---
title: "Week 2 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

* **Topic:** AWS Firewall Manager
* **Main Objective:** Centralized firewall policy management, rule enforcement, and common limitations

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Day 1 | - **Plan:** Firewall Manager Overview <br> - **Main Task:** Firewall Manager Basics <br> - **Detailed Activities:** Learned what AWS Firewall Manager is and why it is used in multi-account environments. Understood the main purpose of centralized firewall management | 17/09/2026 | 17/09/2026 | [AWS Firewall Manager Console](https://console.aws.amazon.com/wafv2/fms) <br> [AWS Firewall Manager Developer Guide](https://docs.aws.amazon.com/waf/latest/developerguide/fms-chapter.html) |
| Day 2 | - **Plan:** Central Policies <br> - **Main Task:** Policies & Rules <br> - **Detailed Activities:** Studied how Firewall Manager policies apply security rules to AWS resources and accounts. Understood the difference between central policies and actual firewall rules | 18/09/2026 | 18/09/2026 | [AWS Firewall Manager Console](https://console.aws.amazon.com/wafv2/fms) <br> [AWS Firewall Manager Developer Guide](https://docs.aws.amazon.com/waf/latest/developerguide/fms-chapter.html) |
| Day 3 | - **Plan:** Risk Review <br> - **Main Task:** Limitations & Risks <br> - **Detailed Activities:** Reviewed common problems such as policy conflicts, wrong configurations, and automation issues. Understood that Firewall Manager can enforce policies but cannot automatically fix bad security decisions | 21/09/2026 | 21/09/2026 | [AWS Firewall Manager Console](https://console.aws.amazon.com/wafv2/fms) <br> [AWS Firewall Manager Developer Guide](https://docs.aws.amazon.com/waf/latest/developerguide/fms-chapter.html) |

### Week 2 Achievements:

* **AWS Firewall Manager:** Centralizes firewall policy deployment and visibility across multi-account AWS Organizations
* **Policy vs. Rule Separation:** Distinguishes between central governance policies (which accounts/resources are covered) and underlying firewall rules
* **Operational Risks:** Identifies how misconfigured central policies or overlapping rules can impact multiple accounts simultaneously

AWS Firewall Manager is not a standalone firewall—it is a central management layer that pushes and enforces security policies across accounts and resources. While this automation keeps new resources compliant automatically, it also amplifies the blast radius of a bad configuration: a poorly written central policy can disrupt traffic across many accounts at once.

Key takeaways:

- **Central Orchestrator:** Firewall Manager enforces rules consistently across accounts, but administrators still design the actual security logic.
- **Policy vs. Protection:** Automation guarantees that rules are applied, not that the rules themselves are well-designed.
- **Blast-Radius Awareness:** Central policies must be tested carefully to avoid rule conflicts and unintended blocks across the organization.
