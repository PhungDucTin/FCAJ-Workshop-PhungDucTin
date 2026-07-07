---
title: "Event AWS First Cloud AI Journey Community Day - May 2026"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---


### Event Objectives

- Share practical knowledge and the latest trends in Cloud (AWS) and Artificial Intelligence (GenAI).
- Update on the IT job market landscape in the AI era and how to equip an "AI Mindset."
- Provide guidance on best practices for applying LLMs and building Multi-Agent architectures in enterprise environments.
- Create a space for connection and networking among the community of engineers, students, and industry experts.

### List of Speakers

- **Tinh Truong** - Platform Engineer, GoTymeX
- **Anh Pham** – Cloud Consultant, G-AsiaPacific Vietnam
- **Thinh Nguyen** - Devops Engineer, FCAJ
- **Thao Nguyen** - GenAI Engineer, VIB
- **Mai Nguyen** - GenAI Engineer, VIB
- **Uyen Le** - GenAI Engineer, VIB
- **Duc Dao** - Solutions Architect, Cloud Kinetics
- **Vy Lam** - Senior Business Systems Analyst, VPBank

### Key Highlights

#### The Importance of Context when Communicating with AI (Presented by: Tinh Truong)

- **Avoid the "Internet Puller" trap:** Do not automatically "pull" every tool or code snippet found online without reviewing whether it suits your project/company's system architecture.
- **Context Optimization:** Avoid rambling across multiple topics in a single thread, which dilutes the AI's focus. Clearly define the role, goals, and specific context so the AI can work most effectively.
- **AI Mindset:** Encourages a mindset of applying AI to real-world scenarios to solve specific problems rather than just abusing prompts without direction.

#### Amazon Q Assistant - Automated Business Intelligence (BI) Analysis Solution (Presented by: Anh Pham)

- **Solving traditional BI problems:** Simplifies the process of generating reports and analyzing complex business data through AWS AI assistants.
- **Full Automation:** From a raw Excel data file, users can communicate directly to request Amazon Q to analyze and automatically create intuitive Dashboards in seconds, optimizing decision-making without needing a specialized BI team.

#### Cost Optimization & Security with Amazon CloudFront's Flat-rate Pricing (Presented by: Thinh Nguyen)

- **Flat-rate pricing mechanism:** Solves the fear of "Shock Bills" by fixing monthly CDN costs. Businesses no longer worry about costs reaching tens of thousands of dollars during DDoS attacks or traffic spikes.
- **Advanced Infrastructure Security:** Provides advanced security features like VPC Origin (hiding servers from the public internet, allowing access only via CloudFront), mTLS (mutual TLS authentication), and geo-blocking/access control by region.

#### The 36-hour Hackathon Journey building the UTM Morpo tool (Presented by: Uyen, Thao & Mai)

- **UTM Morpo Project:** Applying AI to generate User Interface/User Experience (UI/UX). The highlight is the feature allowing developers to interact directly (drag-and-drop, edit components, CSS) on the design created by AI to save re-rendering time.
- **Practical Lessons:** Faced real-world barriers such as running out of "tokens" halfway and the phenomenon of AI "over-generation" (generating redundant code/overthinking). Through this, the team learned valuable lessons about pruning features and focusing all resources on the core experience when resources are limited.

#### The Probabilistic Nature of LLMs and Parameter Tuning (Presented by: Duc Dao)

- **LLM Qualitative Issues:** LLMs are essentially probabilistic models. Even when setting temperature = 0 (Greedy decoding), results may still deviate between runs due to decimal rounding in the GPU and inference optimization from the API provider.
- **"Hallucination" Control Strategies:** Instructions on configuring parameters (Top-p, Temperature, JSON Mode) to put LLMs into workflows requiring stability, while emphasizing the importance of extensive testing before deploying models to Production.

#### Building an Enterprise-grade Multi-Agent System for Startup Credit Assessment (Presented by: Vy Lam)

- **Multi-Agent Architecture:** Instead of "stuffing" every task into a single bot, the system is designed by breaking tasks into specialized Agents (Financial Analysis, Risk Assessment, Market Research...) operating under the coordination of an Orchestrator. This helps avoid Context Window overload and improves output accuracy.
- **Security & Compliance:** Bringing AI into enterprises/banks is not just a technical story. AI systems must strictly adhere to Guardrails, prevent MCP (Model Context Protocol) Attack Vectors, and always maintain an Audit Trail to ensure accountability in every decision.

### Key Takeaways

#### AI Application Mindset

- **Context-driven communication:** Do not use AI as a "fast-food" search engine ("Internet Puller"). To make AI solve problems correctly, developers need to set the role, goal, and specific context right from the start, avoiding rambling that dilutes the model's direction.
- **Simplification and core focus:** From the 36-hour Hackathon lesson, when integrating AI into products, do not be "greedy" with features or let AI automatically generate redundant code (over-generation). Know how to "prune" ideas and carefully calculate resource limits (token limits) to ensure the system runs smoothly.
- **Using AI to free up labor:** Complex analysis and data reporting tasks can be fully automated by virtual assistants (like Amazon Q), enabling teams without deep Business Intelligence (BI) expertise to make data-driven decisions.

#### Technical Architecture

- **Shift to Multi-Agent:** For large problems, instead of stuffing every request into a single AI model (which easily causes Context Window overload), breaking the system down into specialized agents (Multi-Agent) under the coordination of an Orchestrator is the key to increasing accuracy and maintainability.
- **Controlling LLM randomness:** Understanding the probabilistic nature of LLMs allows for tuning parameters (Temperature, Top-p, JSON mode) appropriate for each task. Simultaneously, recognize the importance of extensive testing to avoid AI "hallucinations" before going to Production.
- **Cloud infrastructure cost optimization:** Choosing flexible pricing mechanisms like CloudFront's Flat-rate pricing is not just a Sales team issue but also a DevOps issue, ensuring the system can scale comfortably without pushing the business into a "Shock Bill" disaster.

#### Enterprise Standards

- **Security & Compliance is #1:** Good technique is not enough to bring AI into specialized industries like Banking. It is necessary to establish strict Guardrails to control input/output data.
- **Accountability (Audit Trail):** Every autonomous decision of the AI system (such as credit approval, authorization) must be clearly logged, while also blocking risks from vulnerabilities (MCP attack vectors) and protecting the internal network (VPC Origin, mTLS).

### Application to Work

- **Apply AI Mindset & Context Optimization:** Change the way of communicating with AI in the current project, setting context, roles, and clear goals right from the start instead of using general prompts (avoiding the "Internet Puller" trap).
- **Design Multi-Agent Architecture:** Begin researching and experimenting with breaking down complex AI tasks into Multi-Agent systems (with an Orchestrator coordinating specialized Agents) instead of relying on a single LLM model.
- **Optimize and secure Cloud infrastructure:** Review content delivery configurations, consider switching to Amazon CloudFront's Flat-rate pricing. Start applying Terraform (IaC) to manage infrastructure instead of manual operations.
- **LLM Hallucination Testing:** Readjust parameters (Temperature, Top-p, JSON mode) for current AI features and build extensive testing scenarios to ensure stability before Production deployment.
- **Try Amazon Q:** Test integrating Amazon Q into the internal BI process to automate raw file reading and report/dashboard generation.

### Event Experience

Participating in the "AWS First Cloud AI Journey Community Day 2026" was a very rewarding experience, helping me get a comprehensive view of how to apply AI and Cloud in practice, especially in large enterprise environments. Some highlights:

#### Learning from High-Caliber Speakers
- Speakers from AWS, VPBank, VIB, and major tech organizations shared **best practices** in modern AI system design.
- Through practical case studies (like the startup credit scoring problem), I better understood how to apply **Multi-Agent System** architecture and how to set Enterprise Standards into large projects.

#### Practical Technical Experience
- Participating in in-depth presentations helped me visualize the **probabilistic** nature of LLMs and the real reasons behind result deviations between runs.
- Learned how to identify and prevent system security risks, especially managing vulnerabilities through **MCP attack vectors**.
- Learned practical lessons from the 36-hour Hackathon project (UTM Morpo) on how to control resource limits (token limits) and the skill of "pruning" ideas to avoid AI over-generation.

#### Using Modern Tools
- Directly learned about the Data/BI automation capabilities of **Amazon Q**, turning dry Excel data into intuitive Dashboards in seconds.
- Gained deeper insight into infrastructure tools like **Amazon CloudFront** with Flat-rate pricing models and powerful network protection layers like **VPC Origin** or **mTLS**.

#### Networking and Exchange
- The workshop created opportunities for direct exchange with experts and colleagues in the Cloud and AI industry, helping to expand networking and define the stringent requirements of the current job market more clearly.
- Through practical examples, I realized the importance of a **Business-first approach** and **AI Mindset**, always starting from understanding the business problem correctly rather than abusing technology aimlessly.

#### Lessons Learned
- Applying **Multi-Agent** architecture helps reduce memory limits (Context Window), increasing accuracy and scalability for AI systems.
- Bringing AI into the enterprise environment requires strict adherence to **Security & Compliance**; always set Guardrails and an Audit Trail system to ensure accountability.
- When deploying products, do not rush to "stuff" features. Focus on core value, continuous testing, and optimizing infrastructure operating costs.

#### Photos from the event

<h4 align="center"><em>Check-in photo at the event</em></h4>

![Check-in photo at the event](anh1.jpg)

<h4 align="center"><em>Event group photo</em></h4>

![Event group photo](anh2.jpg)

> Overall, the AWS First Cloud AI Journey Community Day - May 2026 event is a panorama of how to apply cloud computing (AWS) and Artificial Intelligence (GenAI) into the enterprise environment, helping attendees level up their mindset from a mere coder to a Problem Solver.