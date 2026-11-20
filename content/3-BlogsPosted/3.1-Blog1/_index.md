---
title: "Blog 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---
# AMAZON INSPECTOR – HOW DOES AWS AUTOMATICALLY SCAN VULNERABILITIES FOR YOUR SYSTEM?

<img src="../../images/blog1/post.jpg" alt="Proof of Post on AWS Study Group VN" width="700" style="border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;" />

**Link to the original post:** [AWS Study Group VN – Facebook](https://www.facebook.com/share/p/19zsn47hkx/)

Security is often thought of mainly as configuring IAM permissions and closing unnecessary ports. However, a server can be well-configured and still be compromised simply because the software inside remains unpatched. A single outdated library or an unpatched OS package is enough to give attackers a way in.

### 1. WHAT IS AMAZON INSPECTOR?

Simply put, it is AWS's automated vulnerability management service. Once enabled, it automatically discovers your running workloads and scans them for software vulnerabilities as well as unintended network exposure to the Internet. You do not need to schedule scans or trigger them manually.

<img src="../../images/blog1/architecture.jpg" alt="Amazon Inspector Architecture Diagram" width="700" style="border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;" />

### 2. HOW DOES IT WORK?

It operates in 3 main steps:

- **Input Data (Resource Discovery):** Inspector automatically discovers what needs to be scanned: EC2 instances (using SSM Agent or agentless scanning), container images in Amazon ECR, AWS Lambda functions, and source code in code repositories. You only need to enable the service without registering each resource manually.
- **Analysis & Evaluation:** Inspector correlates running software against the CVE database (publicly disclosed vulnerabilities). Whenever a new CVE is published, it automatically rescans your environment—meaning a system that was "clean" yesterday is not guaranteed to be clean today. In addition, it evaluates whether the resource is reachable from the Internet (Network Reachability) and whether the vulnerability is actively exploitable in the wild (Exploitability). Based on these factors, each finding is assigned a contextual **Inspector Risk Score**.
- **Findings & Automated Response:** Findings are aggregated in the Inspector console and pushed to AWS Security Hub for centralized visibility. Findings are also routed through Amazon EventBridge, allowing you to build automated remediation workflows—for example, invoking AWS Lambda to create support tickets, triggering SSM Patch Manager to apply patches, or sending alerts via Amazon SNS. Note that Inspector detects and reports vulnerabilities, while automated patching is an additional workflow you integrate.

For the exact same vulnerability, if it resides on an Internet-facing server, its score will be significantly higher than on an internal-only instance. This helps teams prioritize what to patch first instead of staring at a list of hundreds of CVEs without knowing where to start.

### 3. PRICING & TARGET AUDIENCE

**Pricing:**
Inspector uses pay-as-you-go pricing based on usage, with no upfront commitment or minimum fee. New accounts receive a 15-day free trial for each scan type, allowing you to enable it, assess how many vulnerabilities exist in your environment, and estimate monthly costs. Note that CIS Benchmark assessments are excluded from the free trial. Detailed pricing varies by AWS Region and can be checked on the official AWS pricing page.

**Who is it for?**
It is ideal for small and medium-sized businesses without a dedicated security team, or modern cloud architectures running containers, Lambda functions, and frequently updated third-party libraries—environments where tracking vulnerabilities manually is nearly impossible.

### 4. CONCLUSION

The true value of Amazon Inspector does not lie in merely listing vulnerabilities—many tools can do that. What sets it apart is contextual risk scoring based on your system's real-world exposure, helping you know exactly what to remediate first. Combined with Amazon EventBridge, the entire pipeline from detection and notification to remediation can run almost completely automatically.

**References:**
- [Amazon Inspector – Official Documentation](https://docs.aws.amazon.com/inspector/latest/user/what-is-inspector.html)
- [Amazon Inspector – Pricing](https://aws.amazon.com/inspector/pricing/)

*[#AWS](https://www.facebook.com/hashtag/AWS) [#AmazonInspector](https://www.facebook.com/hashtag/AmazonInspector) [#CloudSecurity](https://www.facebook.com/hashtag/CloudSecurity) [#FCAJ](https://www.facebook.com/hashtag/FCAJ)*
