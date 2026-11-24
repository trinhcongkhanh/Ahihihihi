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

- Before this talk, I mostly thought about which model to choose. Now I would start with what the bot must do and what can go wrong
- Latency, cost and accuracy pull against each other, so they need to be discussed before building, not after

#### Technical Architecture

- RAG, context control and guardrails each solve a different problem, and a reliable bot needs all three
- Managed AWS services (Bedrock, Lambda, API Gateway, Secrets Manager) leave more time for the logic of the bot itself
- A secret that reaches a repository should be treated as already exposed

#### Career Mindset

- Saying clearly what I do not know is better than guessing
- A small project explained well with STAR can say more than a long list of tools

### Applying to Work

- **Design project chatbots** with RAG and selective context management instead of sending the whole history to the model
- **Add guardrails** such as input filtering and prompt-injection checks to any bot I build
- **Try Amazon Bedrock Knowledge Bases** for a small question-answering prototype
- **Use Lambda and API Gateway** for lightweight bot backends
- **Move credentials to AWS Secrets Manager** in my projects
- **Practice STAR answers** based on my AWS labs and course projects

### Event Experience

I came to **“The Thinking Behind Building The Bot”** expecting to hear mainly about models and prompts. What stayed with me instead was how much careful work happens around the model.

#### Learning from the speaker
- The speaker kept returning to architecture, which made me look at chatbots from the system side rather than the prompt side.
- The parts on context management and RAG explained why a bot can sound confident and still be wrong.

#### Technical exposure
- Seeing Bedrock, Lambda, API Gateway and Secrets Manager placed in one picture helped me connect services I had been learning separately.

#### Mock interview and career guidance
- Watching the mock interviews made me realize that how a candidate reasons matters more than a perfect answer.
- STAR gave me a simple order to follow when I talk about my labs and projects.

#### Networking and discussions
- Talking with engineers from CMC Global and AWS mentors gave me a clearer idea of how cloud and information security meet in real work.

#### Lessons learned
- A bot should be judged by how it behaves in difficult cases, not only by a good demo.
- As an Information Assurance student, I should ask early what data the bot can reach and who can reach it.
- I need to practice explaining my work simply, because good technical work still has to be understood by others.

#### Some event photos
![Check-in photo with visible face verifying participation in The Thinking Behind Building The Bot](../../images/event1.jpg)

> I left the talkshow with a different first question: not “which model should I use?”, but “what does this system need to be trusted?”
