---
title: "Event 1"
date: 2026-09-26
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Summary Report: “The Thinking Behind Building The Bot”

### Event Information

- **Time**: Saturday, 26/09/2026, 09:00 – 12:00
- **Location**: 26F, Bitexco Financial Tower, Ho Chi Minh City
- **Participation Role**: Attendee
- **Organizers**: CMC Global in cooperation with AWS First Cloud Journey
- **Format**: In-person talkshow, combined with a Buildathon kickoff and a mock interview session

### Event Objectives

- Show that building an enterprise bot takes far more than calling an LLM API
- Explain the design mindset behind reliable bots: architecture, context handling, latency, cost and data protection
- Present how to deploy bots on AWS with Amazon Bedrock and serverless services
- Give participants practical career advice through mock interviews

### Speakers

- **Bui Nhat Truong** – Technical Leader, CMC Global

### Agenda

| Time | Activity | Details |
|---|---|---|
| 09:00 – 09:30 | Buildathon Kickoff | Launch of the technical challenge series, explanation of the rules and evaluation criteria, and team networking |
| 09:30 – 11:15 | Talkshow: The Thinking Behind Building The Bot | System design, data flow, RAG architecture and LLM orchestration on AWS |
| 11:15 – 12:00 | Mock Interview and Career Coaching | Live mock interviews for Cloud/AI roles, feedback on answers and open Q&A |

### Key Highlights

#### Enterprise-grade bot mindset

A bot for business use differs greatly from a chat window where someone types a prompt:

- **Context management**: keep only the useful parts of the conversation history, which lowers token cost and avoids overflowing the context window
- **RAG (Retrieval-Augmented Generation)**: ground answers in the company's own data through embedding models and a vector database
- **Guardrails and safety**: filter harmful input, defend against prompt injection and keep answers within company policy

#### Deploying on AWS

- **Amazon Bedrock and Knowledge Bases**: access several foundation models through one standard API, with RAG built in
- **Serverless compute**: AWS Lambda and Amazon API Gateway handle event-driven webhooks and cost almost nothing while idle
- **Credential security**: store API keys and secrets in AWS Secrets Manager rather than hardcoding them in source code

#### Quote from the speaker

> A great AI assistant is not decided by having the biggest model, but by sound architecture: how latency is controlled, how accurate the information is, and how well the system recovers from unexpected cases.

#### Mock interview session

- **Interviewer's view**: Tech Leads and Solution Architects value problem-solving ability, honesty about what you know and the ability to learn on your own, more than memorized syntax
- **STAR method**: describe lab work and projects as Situation → Task → Action → Result
- **Networking**: a chance to talk directly with engineers from CMC Global and AWS

### Key Takeaways

#### Design Mindset

- Treat a bot as a system to be engineered, not as a prompt wrapped around a model
- Plan for latency, cost, accuracy and failure from the start

#### Technical Architecture

- Combine RAG, context control and guardrails to keep answers relevant and safe
- Use managed AWS services (Bedrock, Lambda, API Gateway, Secrets Manager) to keep deployment simple and cost-efficient
- Keep secrets out of repositories

#### Career Mindset

- Show how you think, not only what you remember
- Use the STAR structure to present hands-on AWS projects clearly

### Applying to Work

- **Design project chatbots** with RAG and selective context management instead of sending the whole history to the model
- **Add guardrails** such as input filtering and prompt-injection checks to any bot I build
- **Try Amazon Bedrock Knowledge Bases** for a small question-answering prototype
- **Use Lambda and API Gateway** for lightweight bot backends
- **Move credentials to AWS Secrets Manager** in my projects
- **Practice STAR answers** based on my AWS labs and course projects

### Event Experience

Attending **“The Thinking Behind Building The Bot”** gave me a practical view of what sits behind a bot that works reliably in a company.

#### Learning from the speaker
- The talk showed that model choice is only one part of the picture; architecture decisions matter just as much.
- Examples of context management and RAG made the ideas concrete.

#### Technical exposure
- I saw how Bedrock, Lambda, API Gateway and Secrets Manager can fit together in one bot deployment.

#### Mock interview and career guidance
- Watching live mock interviews showed what interviewers look for in fresher candidates.
- The STAR method gave me a clear way to talk about my own projects.

#### Networking and discussions
- I had the chance to meet engineers from CMC Global and AWS mentors and ask about career paths in cloud computing and information security.

#### Lessons learned
- A strong bot comes from disciplined design, not only a powerful model.
- Security habits, such as managing secrets properly, should be built in from the start.
- Clear, honest communication of how you solve problems matters in interviews.

#### Some event photos
![Check-in photo with visible face verifying event participation](../../images/event1.jpg)

> Overall, the talkshow changed how I see chatbot projects: as engineered systems that must be fast, accurate, safe and affordable.
