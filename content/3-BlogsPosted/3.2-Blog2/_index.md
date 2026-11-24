---
title: "Blog 2"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---
# OPENING THE AWS BILL EVERY MONTH AND ASKING “WHY DID COSTS SPIKE?” — WHAT IF AN AGENT FOUND THE ANSWER AUTOMATICALLY?
### AUTOMATING CLOUD FINANCIAL MANAGEMENT WITH AWS FINOPS AGENT

<img src="../../images/blog2/post.jpg" alt="Proof of Post on AWS Study Group VN" width="700" style="border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;" />

**Link to the original post:** [AWS Study Group VN – Facebook](https://www.facebook.com/share/p/1R7PLrnFum/)

In many organizations, cloud cost management still operates on a periodic cycle. At the end of the month, the FinOps team opens a dashboard and discovers an abnormal cost spike in a service. They then have to filter data in Cost Explorer, correlate it with infrastructure change history, and ask individual teams who created or modified resources.

This process is time-consuming. More importantly, it is reactive: by the time the root cause is identified, the cost has already been accumulating for days. This raises a key question: does cost investigation really have to wait for monthly review meetings, or can it happen the moment an anomaly appears?

AWS FinOps Agent entered public preview on 09/06/2026. Built on Amazon Bedrock, this frontier agent is designed to answer cost questions, automatically investigate cost anomalies, and execute recurring FinOps workflows. This approach shifts Cloud Financial Management from manual periodic reviews to continuous, event-driven operations.

### 1. WHAT PROBLEM DOES AWS FINOPS AGENT SOLVE?

FinOps (Financial Operations) is a discipline that connects finance, engineering, and business teams. Its goal is to maximize the business value of cloud investments through shared financial accountability and data-driven decision-making.

The challenge is that cost data and operational data often live in separate silos. Cost Anomaly Detection can alert you that spending is rising, but it does not tell you which infrastructure change caused it, who owns the resource, or how to remediate it. That investigation still relies heavily on human effort.

AWS FinOps Agent takes on this exact responsibility. Engineers can ask questions in natural language, such as “Why did our AWS costs increase last month?”. The agent responds based on actual cost and usage data: how much spending changed, which services contributed the most, and which specific usage factors drove the increase.

### 2. ARCHITECTURE AND CORE COMPONENTS

<img src="../../images/blog2/architecture.jpg" alt="AWS FinOps Agent Architecture Diagram" width="700" style="border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;" />

The agent is provisioned inside an AWS account, runs in the US East (N. Virginia) Region, and users interact with it through a chat-based web application.

Amazon Bedrock provides the foundation models for reasoning and investigation planning.

On the data side, the agent integrates several existing AWS services:

- **AWS Cost Explorer:** cost and usage data.
- **AWS Cost Anomaly Detection:** emits events when spending anomalies occur.
- **AWS Cost Optimization Hub and AWS Compute Optimizer:** recommendations for rightsizing, idle resources, and Savings Plans.
- **AWS CloudTrail:** audit logs of who changed what, and when.

Notably, the agent does not create a new cost data silo. Instead, it sits above the cost management services the organization already uses and connects them into a unified investigation workflow.

Additionally, teams can upload context files such as account-to-owner mappings, team definitions, tagging conventions, or review cadences. The agent applies this organizational context to its answers and retains memory across sessions.

Results are delivered directly to the tools engineers already use: posting investigation reports to Slack or opening tickets in Jira.

### 3. HOW DOES COST ANOMALY INVESTIGATION WORK?

The agent can be configured to listen for events from Cost Anomaly Detection.

When an alert is triggered, the agent correlates the cost fluctuation against events in AWS CloudTrail. From there, it identifies which infrastructure change led to the spike and compiles an investigation report detailing the likely root cause and the responsible owner.

The report is sent to a Slack channel or created as a Jira ticket, allowing engineering teams to receive actionable insights without manual triage.

Alongside this event-driven model, the agent can also run scheduled workflows defined by users—for example, generating periodic cost reports for finance and engineering teams.

### 4. ACCESS CONTROL AND SECURITY

When an AI agent is granted access to financial and operational data, access control becomes critically important.

The agent accesses data through a customer-managed IAM role. Organizations can restrict which accounts, services, and actions the agent is allowed to use, strictly following the principle of least privilege.

AWS also provides blast-radius controls and rollback mechanisms. Users can define boundaries across dimensions such as accounts, Regions, or maximum financial impact.

All agent activities are logged in AWS CloudTrail within the host account, creating a complete audit trail to verify what the agent accessed and when.

### 5. GETTING STARTED

According to AWS documentation, the setup process consists of five steps:

1. Sign in to the AWS Management Console, switch to the `us-east-1` Region, and open the AWS FinOps Agent console to create your first agent.
2. Configure the IAM role with a single click. This customer-managed role allows the agent to read cost, usage, and operational data.
3. Connect Jira and Slack (optional).
4. Review the agent configuration.
5. Launch the web application to start interacting with the agent.

### 6. LIMITATIONS TO CONSIDER

Although AWS FinOps Agent significantly reduces manual investigation overhead, it is still in preview. Features and scope may change before General Availability (GA).

During the preview period, the agent is only hosted in US East (N. Virginia). Cost data covers all AWS Regions except AWS GovCloud (US) and Regions in China. The service is free during preview but subject to monthly usage limits and service quotas. GA pricing has not yet been announced, so total cost of ownership cannot be fully evaluated yet.

The agent only works with AWS data. Organizations operating in multi-cloud environments will still need additional tools for a consolidated cross-cloud cost view.

Answer quality also depends on input data quality. If resource tagging is inconsistent or owner mappings are outdated, the agent will struggle to pinpoint the exact responsible team.

Finally, the agent does not replace the FinOps team. Root cause conclusions still require human verification before making infrastructure changes or committing to Savings Plans.

### CONCLUSION

Having a cost dashboard does not automatically mean having cost control. What truly matters is delivering anomaly insights to the right person, at the right time, with a clear enough root cause to take action.

AWS FinOps Agent is a promising approach for organizations with multiple accounts and teams that frequently spend hours investigating cost fluctuations.

However, real-world effectiveness depends on proper IAM permission scoping, tagging hygiene, organizational context, and the eventual GA pricing model.

Cloud cost optimization is not just about cutting resources—it is about closing the gap between the moment a cost anomaly occurs and the moment the team truly understands why.

**References:**
- [AWS What’s New – AWS FinOps Agent preview](https://aws.amazon.com/about-aws/whats-new/2026/06/aws-finops-agent-preview/)
- [AWS Blog – Announcing the public preview of AWS FinOps Agent](https://aws.amazon.com/blogs/aws-cloud-financial-management/aws-finops-agent-is-now-public-preview/)
- [AWS FinOps Agent FAQs](https://aws.amazon.com/finops-agent/faqs/)
- [AWS Blog – Automation and Trust in FinOps](https://aws.amazon.com/blogs/aws-cloud-financial-management/automation-and-trust-in-finops/)

*[#AWS](https://www.facebook.com/hashtag/AWS) [#AWSFinOpsAgent](https://www.facebook.com/hashtag/AWSFinOpsAgent) [#FinOps](https://www.facebook.com/hashtag/FinOps) [#AmazonBedrock](https://www.facebook.com/hashtag/AmazonBedrock) [#CloudFinancialManagement](https://www.facebook.com/hashtag/CloudFinancialManagement) [#AWSStudyGroup](https://www.facebook.com/hashtag/AWSStudyGroup)*
