---
title: "Blog 1"
date: 2026-04-20
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Architectural Discussion of the 'Mini Social Network' Project – Applying the 3-Tier Architecture Model on the AWS Platform

---

Hello to all members of the AWS Study Group VN community.

Our team is currently finalizing our internal social network project called "Mini Social Network." Applying practical knowledge and design principles from the AWS FCAJ program, we have decided to plan and deploy the entire project infrastructure on the AWS Cloud environment according to the standard 3-Tier Architecture model to ensure maximum data isolation and security.

To standardize the documentation in the style of AWS Whitepapers, our team has built a logical architecture diagram within the AWS Region boundary to clearly depict the network structure. To make it easy to follow the system flow, we have divided it into two distinct components:

*   **Data Plane (User Access & Data Flow):** Sequentially routed using numbers [1] to [7].
*   **Control Plane (System Operations & Monitoring):** Marked with letters [A] to [E].

Below is a detailed interpretation of the system's operational mechanism. Our team looks forward to receiving feedback and contributions from the community.

---

## I. DATA PLANE: USER ACCESS & DATA PROCESSING SUB-SYSTEM

### 1. Edge & User Access Layer
*   **[1] Load Web App:** The Frontend interface (developed with React + Vite) is bundled and stored statically on Amazon S3 (Static Website). The user's browser loads UI resources directly from here, optimizing costs and completely reducing the load on the backend processing infrastructure.
*   **[2] API Requests:** When users interact (posting, commenting, liking), API requests from the client are sent via the Internet Gateway (IGW) to enter the isolated Virtual Private Cloud (VPC).

### 2. Public Subnet & Security Control Layer
*   **[3] Filter Malicious Traffic:** Traffic from the Internet Gateway must pass through AWS WAF (Web Application Firewall) for filtering. Here, we configured rulesets to block common attacks like SQL Injection, Cross-Site Scripting (XSS), or spam requests.
*   **[4] Route Traffic:** Clean and valid traffic is then forwarded to the Application Load Balancer (ALB) for load distribution.

### 3. Private Subnet & Core Processing Layer
*   **[5] Process Backend Logic:** ALB distributes requests evenly to the Amazon ECS Cluster. This is where Docker containers running the social network's application logic reside, completely isolated within the Private Subnet - Compute layer to prevent any unauthorized direct access from the Internet.
*   **[6] Read / Write Data:** When querying or writing user information, the ECS cluster communicates with the Amazon RDS database. This DB layer is hidden in the deepest security layer: the Private Subnet - Data.
*   **[7] Upload Media Files:** For heavy resources like images and videos uploaded by users, the ECS cluster routes and pushes them directly to an independent Amazon S3 bucket (Media Storage) for archiving, avoiding capacity and bandwidth burdens on the main database.

---

## II. CONTROL PLANE: OPERATIONS, CI/CD & MONITORING SUB-SYSTEM

This is the infrastructure backbone serving management and automation tasks, running entirely independently of the end-user experience:

*   **[A] Outbound Traffic:** To allow container servers in the Private Subnet (which lack public IPs) to safely reach the Internet for tasks, we deployed a NAT Gateway in the Public Subnet. From here, traffic continues to be routed (Route Outbound Traffic) through the Internet Gateway (IGW) to reach the public network. This is a vital one-way traffic flow allowing internal systems to safely communicate externally (such as pulling Image updates from ECR or pushing logs to CloudWatch) without ever revealing the true identity or real IP address of the servers.
*   **[B] Push Logs & Metrics:** Through the NAT Gateway, the ECS cluster continuously collects and pushes system log data to Amazon CloudWatch.
*   **[C] Visualize Dashboard:** We set up Grafana Cloud, connecting directly to Amazon CloudWatch as a Data Source to visualize infrastructure health and CPU/RAM resources via real-time monitoring charts.
*   **[D] Build & Push Image:** The CI/CD pipeline starts from the Jenkins Server (responsible for automating testing and building backend source code into new Docker images) and proceeds to push them to the Amazon ECR registry.
*   **[E] Pull Image & Deploy:** The ECS cluster uses the Outbound path to automatically pull the latest Image updates from ECR and executes a Rolling Update mechanism, ensuring the system remains uninterrupted (Zero-Downtime).

---

## III. DIRECTIONS AND QUESTIONS FOR COMMUNITY DISCUSSION

Although the diagram shows the AWS Region boundary clearly for global planning, the Subnet structure inside the VPC has been simplified (grouped into one column) to optimize visual clarity.

In reality, within our CloudFormation (IaC) file, we have implemented a much more robust infrastructure than depicted. The system is running on a Multi-AZ architecture – splitting Public/Private Subnets across two different physical Availability Zones to ensure high reliability. Combined with this is the strict configuration of Security Group firewalls (Backend ECS is configured to only receive data from the ALB via port 8080 and no other streams).

Although the PoC (Proof of Concept) system is running smoothly, to upgrade to Production-ready standards, our team has outlined an optimization roadmap (Phase 2) and we look forward to receiving "hard-earned" advice from experienced members:

1.  **Frontend Performance Upgrade (CloudFront):** We realize that users accessing the S3 Static Website directly creates a bottleneck regarding global loading speed and lacks SSL/TLS security. Our next plan is to put Amazon CloudFront (CDN) in front. However, when integrating CloudFront + WAF + S3, do you have any practical advice regarding hidden costs or cache invalidation issues when deploying Frontend code frequently?
2.  **Trade-off: NAT Gateway vs VPC Endpoints:** The ECS cluster currently uses NAT Gateway to reach the Internet to call AWS services (S3, ECR, CloudWatch). To optimize Data Transfer costs and increase internal security, we plan to switch to VPC Endpoints (Gateway/Interface). For small/medium-scale projects, maintaining the hourly cost of Interface Endpoints versus the Data Transfer cost of NAT Gateway—at what traffic level is the actual break-even point?
3.  **Migrating CI/CD to Cloud-Native:** Currently, our team is self-hosting a Jenkins Server on EC2 for source code building. In the long run, to completely cut the maintenance burden and optimize costs (Pay-as-you-go), we plan to migrate the entire pipeline to GitHub Actions or AWS CodePipeline. If migrating the CI/CD architecture, based on your practical experience, what is the most optimal solution for a containerized system on ECS?

## IV. Architecture diagram of the "Mini Social Network" project
![Architecture Diagram](anh1.png)
> Blog on AWS Study Group: Blog post link https://www.facebook.com/groups/awsstudygroupfcj/permalink/2179386592826301
<br>
> Our team sincerely thanks you for all feedback, contributions, and "valuable bricks" that help us build a more complete system from the community!