---
title: "Event 2"
date: 2026-10-02
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Summary Report: “Navigating the Future of Cloud & AI in Vietnam”

The event featured a keynote by Werner Vogels, CTO of Amazon, on lessons from operating large-scale systems and the role of developers in the AI era.

### Event Information

* **Event Name:** Navigating the Future of Cloud & AI in Vietnam
* **Date & Time:** 02/10/2026, 09:00 – 12:00
* **Venue:** Bitexco Financial Tower, Ho Chi Minh City
* **Participation Role:** Attendee
* **Core Learning:** Lessons from operating large-scale systems and the profile of a “Renaissance Developer”

### Event Objectives

- Share why Amazon had to build its own core technology when existing solutions could no longer meet its scale
- Present the principles for operating large systems reliably
- Address whether developers will be replaced as AI automates coding
- Point out the qualities developers need to build in order to keep up

### Speakers

- **Werner Vogels** - CTO, Amazon

### Key Highlights

#### From a multi-million-dollar outage to homegrown core technology

- When Werner Vogels left Cornell University to join Amazon more than two decades ago, no existing software could meet the company's scale
- On a peak shopping day, 12/12, the relational database cluster was overloaded and a latent bug disrupted customer data storage for a day, costing millions of dollars
- The vendor said Amazon had been using the product beyond its design limits

Amazon then re-examined how its databases were used:

| Query type | Share | Characteristics |
|---|---|---|
| **Key-value** | About 70% | Simple lookups, such as fetching a cart by ID |
| **Single table** | About 20% | Work on one table, without links |
| **Relational** | About 10% | Truly need relational database features |

Based on this result, Amazon built its own distributed key-value store, the foundation of Dynamo and DynamoDB.

#### Four pillars of operational excellence

| Pillar | Meaning |
|---|---|
| **Measure at P99.9** | Median latency hides the experience of the half of users with worse results, so the slowest group must be watched |
| **Everything Fails All the Time** | The architecture must survive the sudden loss of one or two data centers without service disruption |
| **GameDays** | Deliberately disconnect production data centers as a drill, remove manual steps, and automate data sync on recovery |
| **Inverting the IT economic model** | Pay-as-you-go replaces long upfront contracts, so the provider must serve well every day to keep customers |

#### Profile of a “Renaissance Developer”

Developers remain valuable if they are willing to change. The speaker named five qualities:

- **Curiosity and continuous learning**: never stop exploring new technology
- **Systems thinking**: understand how microservices interact at scale, not just one separate module
- **Ownership**: AI can generate code, but engineers remain responsible for production bugs, security, and architecture
- **T-shaped expertise**: go deep in one field and broadly understand adjacent ones such as UI, business logic, and databases
- **Communication**: find the real problem behind hype-driven requests and explain trade-offs, such as the cost gap between 99.99% and 99% uptime

#### AI as a catalyst, humans at the core

- AI has cut prototyping time from weeks to hours
- AI was compared to a natural-language compiler that is not fully precise, so its output needs human review for security, edge cases, and efficiency
- AI handles repetitive work well, while judgment, creativity, empathy, and professional pride still belong to humans

#### A quote shared in the talk

> “We've always done it this way” is the most dangerous phrase, according to Grace Hopper's warning repeated by the speaker.

### Key Takeaways

#### Architecture Mindset

- Analyze how data is really accessed before choosing a database
- At very large scale, depending on existing solutions can become an operational risk

#### Operations Mindset

- Design with the assumption that every component can fail
- Recovery can only be trusted once it has been rehearsed
- Averages and medians are not enough to judge user experience

#### Career Mindset

- Use AI to work faster but stay responsible for the result
- Build both technical depth and communication skills

### Applying to Work

- **Choose databases by query pattern**, preferring DynamoDB for key-value lookups
- **Track latency by percentile** in CloudWatch instead of looking only at the average
- **Design for failure** with retries, Dead Letter Queues, and alarms
- **Run small-scale failure drills** in a lab environment
- **Review AI-generated code carefully**, especially for security and edge cases

### Event Experience

Attending **Navigating the Future of Cloud & AI in Vietnam** gave me a clearer view of what lies behind a large-scale system and the role of engineers when AI is there to help.

#### Learning from the speaker
- The story of the database outage showed me that a good architecture decision starts with understanding your own data.
- The five qualities of a “Renaissance Developer” gave me a clear framework for self-assessment.

#### Perspective on AI
- I understood that AI changes how we work, but responsibility for security and quality still belongs to engineers. This is close to Information Assurance, the major I am studying.

#### Lessons learned
- Reliable systems are built by accepting that failures will happen.
- Continuous learning and systems thinking matter more than only knowing how to use one tool.
- A way of working should not be kept just because it has always been done that way.

**Reference:** [The Invariable Lessons of Tech and Humanity: Key Takeaways from Amazon CTO Werner Vogels – Le Vu Xuan An, AWS Builder Center](https://builder.aws.com/content/3KBSLeKsdkk6uMUPq7d9Xxa5jbS/the-invariable-lessons-of-tech-and-humanity-key-takeaways-from-amazon-cto-werner-vogels)

#### Some event photos

![Check-in photo with visible face verifying participation in Navigating the Future of Cloud & AI in Vietnam](../../images/event2-checkin.jpg)

*Event Check-in Verification — Community Workshop*

> Overall, the event helped me understand that technology changes quickly, but systems thinking, responsibility, and continuous learning remain the foundation of an engineer.
