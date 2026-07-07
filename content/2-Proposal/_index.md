---
title: "Proposal"
date: 2026-07-01
weight: 2
chapter: false
pre: "  2.  "
---

# Mini Social Network (MiniSocial)

## A Cloud-Native AWS Infrastructure with Automated CI/CD Pipelines and Gamification

### Project Snapshot
- A full-stack social platform designed as an academic showcase of modern cloud engineering.
- Built to support 20–100 concurrent users while remaining cost-efficient and easy to scale.
- Combines AWS, Containers, CI/CD automation, security controls, and monitoring into one production-oriented blueprint.
- Emphasizes reliability, operational visibility, and practical DevOps implementation.

To give readers a clearer view of the overall concept, the architecture diagram below illustrates the end-to-end flow of the proposed solution.

![MiniSocial Architecture](/Minisocial-Architect_final.png)

### 1. Executive Summary
The Mini Social Network (MiniSocial) is a miniature social network platform integrated with gamification features, designed as a production-grade academic project to demonstrate advanced DevOps and Cloud Engineering workflows. The platform is designed to reliably serve 20 to 100 concurrent users, featuring high scalability through a cloud-native architecture. Deployed entirely on AWS using Infrastructure as Code (IaC) via CloudFormation and managed automatically by external Jenkins CI/CD pipelines, this platform showcases enterprise best practices in security, automated testing, real-time monitoring, and proactive cost optimization.

### 2. Problem Statement

### What’s the Problem?
Building and deploying a modern fullstack social network application requires addressing significant infrastructure complexities. Traditional environments often lack streamlined, automated deployment pipelines, resulting in friction between development and operations. Additionally, maintaining real-time features (such as chat and notifications) alongside database-driven applications on public clouds can easily lead to high operational costs, security vulnerabilities, and a lack of granular monitoring, which hinders production readiness proof-of-concepts.

### The Solution
The MiniSocial platform tackles these challenges by utilizing a robust AWS serverless and containerized architecture. The frontend is built using React 19, TypeScript 5.9, and Vite, securely hosted on Amazon S3 and distributed via Amazon CloudFront with Origin Access Control (OAC). The backend is powered by Spring Boot 3.2.6 (Java 17) running inside Docker containers managed by Amazon ECS Fargate across multiple Availability Zones. Data persistence is handled via Amazon RDS for SQL Server positioned securely within private subnets. Continuous Integration and Continuous Deployment (CI/CD) are fully automated through local Jenkins servers utilizing two separate multi-stage pipelines to build, test, and automatically ship code. Cost management is heavily reinforced using AWS EventBridge Scheduler to automate environment sleep cycles and ECS Fargate Spot configurations.

### Benefits and Return on Investment
As an academic portfolio project, the primary return on investment is the empirical proof of capability in deploying production-grade, highly secure systems on AWS. Financially, operational costs are aggressively throttled to approximately $45–$60 USD per month. This is achieved by scheduling automated infrastructure shutdowns between 10:00 PM and 7:00 AM daily (saving ~37.5% runtime), implementing Fargate Spot for redundant tasks (saving ~70% compute costs), and deploying an S3 VPC Gateway Endpoint to completely bypass NAT Gateway data transfer fees. The project offers a highly reusable, modular blueprint with 4 CloudFormation stacks and robust Jenkinsfile templates that can be easily retargeted for future enterprise applications.

### 3. Solution Architecture
The proposed platform is more than a simple web application; it is an end-to-end cloud deployment blueprint designed for both functionality and operational excellence. The architecture is structured around three core principles:
- Secure traffic entry through Route 53 and AWS WAF.
- Resilient application execution on ECS Fargate across multiple Availability Zones.
- Fast and reliable frontend delivery through S3 and CloudFront.

User traffic enters via Amazon Route 53, filtering through AWS WAF to mitigate DDoS and web injection attacks before reaching an Internet-facing Application Load Balancer (ALB) over secured HTTPS. The backend logic is processed by ECS Fargate tasks distributed over private subnets across multiple AZs for high availability, while static assets flow directly through CloudFront CDN.

### AWS Services Used

- **VPC & Networking**: Multi-AZ subnets (Public, Private Compute, Private Data), ALB, NAT Gateway, and S3 VPC Gateway Endpoint.
- **Amazon ECS Fargate**: Serverless container execution for backend application nodes.
- **Amazon ECR**: Secure registry hosting built production Docker images.
- **Amazon RDS for SQL Server**: Managed database service (db.t3.small) hosted in dedicated private data subnets.
- **Amazon S3 & CloudFront**: Secure frontend hosting via OAC and global content delivery.
- **AWS WAF & ACM**: Enterprise-grade web application firewall protection and automated SSL/TLS certificates.
- **Amazon Route 53**: Highly available Domain Name System (DNS) management.
- **AWS SSM Parameter Store**: Centralized, secure configuration and secrets management.
- **Amazon CloudWatch & EventBridge**: System logging, infrastructure metrics, and automated scheduling.

### Component Design

- **Web Frontend**: Built using React 19, TypeScript, and Material UI 7.x, communicating with the backend over Axios and tracking real-time events via STOMP.js over WebSockets.
- **Application Backend**: Spring Boot 3.2.6 core utilizing Spring Security + JWT for stateless authentication, Spring Data JPA for data mapping, and Spring WebSocket for real-time messaging.
- **Database Engine**: Microsoft SQL Server 2022 Express running locally on Docker for development, transitioning seamlessly to Amazon RDS in production.
- **Monitoring Stack**: Micrometer OTLP engine capturing metrics and exporting them directly into a centralized Grafana Cloud dashboard alongside CloudWatch Logs.

### 4. Technical Implementation
**Implementation Phases**
The engineering life cycle of the MiniSocial project is divided into 5 distinct sequential deployment phases:

- Phase 1 — Foundation: Focuses on designing the MSSQL core database schema, engineering backend REST APIs (JWT Authentication, core post CRUD), assembling the React SPA layout, and wrapping the ecosystem in local Docker Compose files.
- Phase 2 — Social Features: Enforces core social interactions, including bidirectional Friend Requests, real-time chat via WebSocket STOMP, conversation handlers, centralized user notifications, and multi-option Post Reactions.
- Phase 3 — Gamification & Cosmetics: Introduces user engaging mechanics like VPTL points system, cosmetic shop items (animated Avatar Frames and custom Name Colors), Gacha/Lootbox mechanics, and interactive mini-games (Snake, Tic-Tac-Toe).
- Phase 4 — Cloud Deployment & DevOps: Provisions 4 separate modular AWS CloudFormation IaC stacks, wires multi-AZ secure networking, setups ECS Fargate clusters, locks down secrets in SSM, and links automated Jenkins CI/CD pipelines.
- Phase 5 — Monitoring & Load Testing: Integrates Micrometer OTLP with Grafana Cloud, scripts stress scenarios using K6 (Normal user journey, DDoS simulation, Feed/Like endpoint saturation), enforces JaCoCo coverage boundaries (≥70%), and executes Selenium E2E suites.

**Technical Requirements**

- Production URL: Hosted live at `https://minisocial-network.id.vn` with backend APIs pointing to `api.minisocial-network.id.vn`.
- CI/CD Automation: Powered by local Windows machine instances running Jenkins, executing multi-stage pipelines bound by dedicated Jenkinsfiles to automatically trigger on GitHub SCM polling.
- Testing Suite: Compulsory test boundaries enforcing a minimum of 70% backend code coverage through JaCoCo automated test phases.

### 5. Timeline & Milestones
**Project Timeline**
The roadmap spans an estimated duration of 1 to 12 weeks from initial architectural drafting to production operation live status:

- Weeks 1-3 (Phase 1): MVP Completion — Core Authentication, REST API endpoints, and functional Docker local environments.
- Weeks 4-6 (Phase 2): Social Integration — Live WebSocket chat infrastructure, notification engines, and friend networks active.
- Weeks 7-8 (Phase 3): Gamification Launch — Operational rewards shop, Gacha algorithms, and canvas mini-games.
- Weeks 9-10 (Phase 4): AWS Infrastructure Go-Live — Automated IaC deployment, active WAF filtering, Route 53 DNS mapping, and running Jenkins pipelines.
- Weeks 11-12 (Phase 5): Quality Assurance & Launch — Comprehensive Grafana monitoring stack setup, K6 load testing reports complete, and JaCoCo coverage benchmarks fulfilled.

### 6. Budget Estimation
The global cloud infrastructure budget estimation is heavily tailored using strict automation workflows to cut unnecessary resource drains.

### Infrastructure Costs
Monthly runtime costs on AWS are structured as follows:

- Amazon ECS Fargate (2 tasks, 0.5 vCPU / 1GB RAM, 15h/day): ~$15.00 – $20.00/month
- ECS Fargate Spot (1 auxiliary task with ~70% cost reduction): ~$3.00 – $5.00/month
- Amazon RDS for SQL Server (db.t3.small, 20GB gp2, 15h/day): ~$10.00 – $15.00/month
- AWS NAT Gateway (1 Instance + data transfer optimizations): ~$5.00 – $8.00/month
- Application Load Balancer (ALB Internet-facing handler): ~$5.00/month
- AWS WAF (Web ACL filtering active): ~$5.00/month
- Amazon S3 & CloudFront (Frontend hosting and media storage): ~$1.00 – $2.00/month
- Amazon CloudWatch & ECR (Log aggregation and image retention): ~$1.00 – $2.00/month
- Amazon Route 53, ACM, SSM, EventBridge Scheduler: ~$0.50/month (Free Tier adjustments applied)
Total Infrastructure Budget: ~$45.00 – $60.00 / month

External Cost Breakdown: Domain purchase (`.id.vn`) at ~$5.00 – $10.00/year; Jenkins Server, Grafana Cloud, and GitHub accounts remain completely within $0 Free Tiers.

### 7. Risk Assessment

#### Risk Matrix

- R1: Fargate Spot Instance Reclamation (Medium Probability, Low Impact) — Spot compute capacity may be claimed by AWS at any moment, creating potential transient instability.
- R2: Infrastructure Budget Overruns / Bill Shock (Low Probability, High Impact) — Public exposure or unoptimized code tracking could scale cloud invoices unexpectedly.
- R3: Single-AZ Database Outage (Low Probability, High Impact) — RDS SQL Server Express limits architecture to a single AZ, exposing the system to a localized cloud failure zone.
- R4: Local Jenkins CI/CD Server Failure (Medium Probability, Medium Impact) — On-premise deployment server crashes or configuration losses could break deployment capability.
- R5: Security & Credentials Leak (Low Probability, High Impact) — Public leaking of application keys or database passwords might lead to malicious infrastructure takeovers.

#### Mitigation Strategies

- R1 (Spot Capacity): Wired an On-Demand base task constraint (Base=1) that guarantees one primary application task never gets reclaimed. ALB automatically paths user requests to active nodes.
- R2 (Budget Overruns): Enforced automated EventBridge schedules to put compute and storage nodes to sleep daily during off-peak windows, completely cutting costs by ~37.5%.
- R3 (Database Protection): Configured automated 7-day rolling backups, strictly enabled StorageEncrypted flags, and attached a Snapshot DeletionPolicy to guard the database instance state.
- R5 (Secrets Management): Stripped all plaintext passwords from codebases, routing all configurations through AWS SSM Parameter Store wrapped inside isolated private application subnets.

#### Contingency Plans

- If Fargate Spot tasks drop unexpectedly, the primary On-Demand service node automatically scales up compute resources.
- If cloud costs cross historical averages, automated alarms will freeze non-essential staging nodes.
- If the local Jenkins server suffers catastrophic system failure, configurations can be redeployed via backed up Jenkinsfile definitions directly into GitHub Actions alternatives.

### 8. Expected Outcomes

#### Technical Improvements
Transitioning from standard local hosting to an enterprise-grade cloud pipeline brings substantial architecture improvements:

- Fully automated, zero-touch deployment pipelines replacing manual FTP/SSH terminal tasks.
- Real-time performance tracking via Grafana Cloud replacing blind production logging.
- Advanced infrastructure security baseline (WAF, SSL, Private Subnet isolation) blocking standard cross-site and injection vulnerabilities.

#### Long-term Value
The primary asset generated is a highly customizable and repeatable DevOps blueprint. The 4 CloudFormation infrastructure stacks can be cloned and parameter-switched to stand up identical scalable networks for external applications within minutes. Additionally, the multi-stage frontend and backend Jenkins files establish robust deployment templates applicable across various software engineering projects.