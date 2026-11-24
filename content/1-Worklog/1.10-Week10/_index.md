---
title: "Week 10 Worklog"
date: 2024-01-01
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

* **Topic:** CI/CD Pipelines
* **Main Objective:** Understand what CI/CD is and build a simple pipeline on AWS that automatically builds and deploys code every time I push to GitHub

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Day 1 | - **Plan:** CI/CD Basics <br> - **Main Task:** Introduction to CI/CD <br> - **Detailed Activities:** Learned the difference between Continuous Integration, Continuous Delivery and Continuous Deployment. Read about the usual pipeline stages: source, build, test and deploy | 09/11/2026 | 09/11/2026 | [AWS CodePipeline User Guide](https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html) <br> [AWS CodeBuild User Guide](https://docs.aws.amazon.com/codebuild/latest/userguide/welcome.html) |
| Day 2 | - **Plan:** AWS Tools <br> - **Main Task:** CodePipeline, CodeBuild & CodeDeploy <br> - **Detailed Activities:** Learned what each AWS service does in a pipeline. Connected my GitHub repository to AWS so the pipeline can get the code | 10/11/2026 | 10/11/2026 | [AWS CodePipeline User Guide](https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html) <br> [AWS CodeBuild User Guide](https://docs.aws.amazon.com/codebuild/latest/userguide/welcome.html) |
| Day 3 | - **Plan:** Build Stage <br> - **Main Task:** Writing a `buildspec.yml` <br> - **Detailed Activities:** Wrote a simple `buildspec.yml` for CodeBuild to install packages, run tests and package the app. Fixed a few build errors by reading the build logs | 11/11/2026 | 11/11/2026 | [AWS CodePipeline User Guide](https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html) <br> [AWS CodeBuild User Guide](https://docs.aws.amazon.com/codebuild/latest/userguide/welcome.html) |
| Day 4 | - **Plan:** Full Pipeline <br> - **Main Task:** Building the Pipeline <br> - **Detailed Activities:** Created a pipeline in CodePipeline with source, build and deploy stages. Pushed a small change to GitHub and watched it go through every stage automatically | 12/11/2026 | 12/11/2026 | [AWS CodePipeline User Guide](https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html) <br> [AWS CodeBuild User Guide](https://docs.aws.amazon.com/codebuild/latest/userguide/welcome.html) |
| Day 5 | - **Plan:** Review <br> - **Main Task:** Approval Step & Good Habits <br> - **Detailed Activities:** Added a manual approval step before deploying. Looked at GitHub Actions as another option and reviewed how to keep the pipeline safe | 13/11/2026 | 13/11/2026 | [AWS CodePipeline User Guide](https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html) <br> [AWS CodeBuild User Guide](https://docs.aws.amazon.com/codebuild/latest/userguide/welcome.html) |

### Week 10 Achievements:

* **CI/CD Workflow:** Automating Source, Build, Test, and Deploy stages across Continuous Integration, Continuous Delivery, and Continuous Deployment
* **AWS CodeSuite & GitHub:** Orchestrating releases with CodePipeline, running `buildspec.yml` builds/tests in CodeBuild, deploying via CodeDeploy, and comparing with GitHub Actions
* **Pipeline Security & Gates:** Keeping secrets out of repositories/`buildspec.yml`, scoping pipeline IAM roles to least privilege, and enforcing manual approval gates before production

Replacing manual file copying and shell commands with an automated **CI/CD pipeline** made software delivery both faster and much more reliable. Watching a GitHub commit automatically trigger **CodePipeline**, run tests defined in `buildspec.yml` on **CodeBuild**, and deploy to the target environment showed me that automation is not just about speed—it guarantees that every change passes the exact same test and approval gates before reaching users.

Key takeaways:

- **Consistent Release Process:** Every commit runs through identical build and test steps defined in `buildspec.yml`, catching errors early via CodeBuild logs.
- **Delivery vs. Deployment Control:** Adding a manual approval stage in CodePipeline gives teams a final review gate before changes go live in production.
- **Secure Pipeline Hygiene:** Never store credentials in Git or `buildspec.yml`, and grant the pipeline IAM role only the minimum permissions required.
