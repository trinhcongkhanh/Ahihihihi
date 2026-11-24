---
title: "Week 4 Worklog"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

* **Topic:** Amazon Cognito & AWS Secrets Manager
* **Main Objective:** Learn how to add user sign-up and sign-in to an application with Cognito, and how to store passwords and API keys safely with Secrets Manager instead of putting them in code

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Day 1 | - **Plan:** Cognito Basics <br> - **Main Task:** Cognito User Pools <br> - **Detailed Activities:** Read about what Cognito is and the difference between User Pools and Identity Pools. Created a User Pool, set a password policy and turned on email verification | 28/09/2026 | 28/09/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html) <br> [AWS Secrets Manager User Guide](https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html) |
| Day 2 | - **Plan:** Sign-up & Sign-in <br> - **Main Task:** App Client, Login Page & MFA <br> - **Detailed Activities:** Created an app client and tested sign-up and sign-in with the Cognito login page. Turned on MFA with an authenticator app. Looked at the ID token, access token and refresh token returned after login | 29/09/2026 | 29/09/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html) <br> [AWS Secrets Manager User Guide](https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html) |
| Day 3 | - **Plan:** Authorization <br> - **Main Task:** Identity Pools & API Gateway <br> - **Detailed Activities:** Learned how Identity Pools give signed-in users temporary AWS credentials through IAM roles. Added a Cognito authorizer to an API Gateway endpoint so only users with a valid token can call it | 30/09/2026 | 30/09/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html) <br> [AWS Secrets Manager User Guide](https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html) |
| Day 4 | - **Plan:** Storing Secrets <br> - **Main Task:** Secrets Manager Basics <br> - **Detailed Activities:** Created a secret to store database credentials and another one for an API key. Learned that secrets are encrypted with AWS KMS. Read the secret back with the AWS CLI | 01/10/2026 | 01/10/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html) <br> [AWS Secrets Manager User Guide](https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html) |
| Day 5 | - **Plan:** Using Secrets Safely <br> - **Main Task:** Rotation & Lambda Access <br> - **Detailed Activities:** Read about automatic secret rotation with a Lambda function. Gave a Lambda function permission to read only one secret and called it from code instead of hard-coding the value | 02/10/2026 | 02/10/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html) <br> [AWS Secrets Manager User Guide](https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html) |

### Week 4 Achievements:

* **Cognito User Pools & Tokens:** Managing sign-up/sign-in, MFA, and JWT tokens (ID, Access, and Refresh tokens) to authenticate application users
* **Identity Pools & API Security:** Exchanging valid logins for temporary AWS credentials and securing API Gateway endpoints with Cognito Authorizers
* **AWS Secrets Manager:** Encrypting database credentials and API keys with KMS, automating secret rotation, and restricting `GetSecretValue` to specific ARNs

This week focused on two essentials of application security: verifying user identity with Amazon Cognito and eliminating hard-coded credentials with AWS Secrets Manager. Testing both services clarified that **User Pools** handle authentication ("who are you?" via JWT tokens), **Identity Pools** handle AWS authorization ("what can you access?" via temporary IAM credentials), and **Secrets Manager** lets backend functions fetch encrypted credentials at runtime instead of storing secrets in source code.

Key takeaways:

- **Authentication vs. Authorization:** User Pools issue tokens for login and API Gateway checks, while Identity Pools map users to temporary IAM roles.
- **Zero Hard-Coded Secrets:** Applications retrieve credentials dynamically from Secrets Manager so keys can be updated or rotated in one place without changing code.
- **Scoped Secret Access:** Each Lambda function should only have `secretsmanager:GetSecretValue` permission for the single secret ARN it requires, with every read audited in CloudTrail.
