---
title: "Blog 2"
date: 2026-04-20
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# A Diary of Bringing an App to the Cloud – From a $35 Lesson to a Cost-Optimized Architecture

---

Greetings to the admins and members of the AWS Study Group VN community. This article summarizes our team's practical experiences during the deployment of the "Mini Social Network" project on the AWS environment.

Previously, we received a question: "Why not just rent a Virtual Private Server (VPS) and deploy the entire source code there for simplicity, instead of setting up complex services on AWS?". In fact, our team had the exact same thought in the early days. However, when we officially started migrating the entire project architecture to the Cloud, we learned some very valuable practical lessons.

---

## I. Mistakes in the Past (The "Before")

In previous personal projects, our team's deployment mindset was quite simple: "Bundle everything into a single server". We usually rented a virtual machine (VPS), manually installed MySQL, ran the Spring Boot Backend directly, and deployed the React Frontend build via Nginx on the same system. Sensitive information like database passwords or JWT secret keys were stored as plaintext directly in the `.env` file. By simply pointing the domain name to the Public IP, the application was up and running.

At that time, the team thought the system was complete. But in reality, this architecture harbored massive risks: there was no security isolation mechanism, and if the database crashed, the entire application would go down.

---

## II. The Turning Point in our Mindset

When migrating to AWS, mechanically applying the theoretical "3-Tier Architecture" revealed several limitations:

*   **Suboptimal costs:** Placing ECS Fargate in a Private Subnet forced the system to maintain a NAT Gateway to pull Docker Images. As a result, the NAT Gateway incurred a cost of ~$35/month, accounting for over 1/3 of the total project budget even though the traffic was still low.
*   **SPA routing errors:** When deploying the Frontend to S3 Static Website Hosting, if users reloaded the page (Refresh) at sub-paths (e.g., `/profile`), the browser immediately returned a 404 error.
*   **Performance bottlenecks:** The load testing process with K6 (simulating 500 users) showed that the 0.5 vCPU Fargate container reached the 100% CPU threshold due to overload in decoding JWT Token signatures, even though the database remained unaffected.

The system required clear separation and deeper specialization in each department.

---

## III. Solutions and Core Knowledge: Optimizing the Cloud-Native Architecture

Instead of continuing to patch minor errors, the team decided to restructure the system closely following the Cost-Optimized Architecture Diagram. Here is how each department solved their specialized problems:

### 1. Infrastructure Team (Cloud/Ops) – Optimizing Cost and Performance
*   **Challenges:** Placing ECS Fargate in a Private Subnet incurred unnecessary NAT Gateway maintenance costs. Additionally, the container's CPU was overloaded when handling a large volume of JWT authentication operations.
*   **Solutions:** Realizing the waste of resources, the Infrastructure team reconfigured ECS Fargate, moving it to Public Subnets (activating `AssignPublicIp: ENABLED`) and completely eliminating the NAT Gateway. To ensure the Zero-Trust principle, Fargate was set up with a Security Group that only accepts traffic from the Application Load Balancer (ALB). The RDS database remained isolated in the Private Subnet. For secure DB management, the team set up a t2.micro EC2 instance (Free Tier) as a Bastion Host in the Public Subnet. Combined with using Amazon EventBridge to automatically shut down the Database and scale the number of ECS containers down to 0 at 11:00 PM, then turning them back on at 7:00 AM, the networking cost was reduced to $0.

### 2. Frontend Team (UI/UX) – Handling Routing Errors and Integrating CloudFront
*   **Challenges:** Hosting a Single Page Application (SPA) on Amazon S3 caused a 404 error when users reloaded sub-pages. Furthermore, the raw S3 configuration did not support HTTPS certificates and had high page load latency for users far from the storage region.
*   **Solutions:** To fix the 404 error, the Frontend team configured the Error document to point to `index.html`, handing the navigation control back to React Router. To optimize content delivery speed and ensure transmission security standards, the system integrated the Amazon CloudFront Content Delivery Network (CDN) at the frontline. The subsequent deployment process was fully automated using a Jenkins CI/CD server (running on EC2), which automatically pulls source code from GitHub, packages it, and pushes it to S3/ECR, minimizing manual operations.

### 3. Observability Team – Proactive Monitoring and Alert Management
*   **Challenges:** System monitoring required an automated mechanism rather than manual supervision. Even though we had integrated AWS CloudWatch, Grafana, and embedded OpenTelemetry (OTLP) into Spring Boot, the biggest problem was how to detect cyberattacks without causing an alert noise issue (Email Storm).
*   **Solutions:** The team set up Metric Filters on CloudWatch to scan application logs using the syntax `{$.type = "SECURITY"}`. The system only triggers a CloudWatch Alarm when it detects scanning behaviors for SQL Injection or XSS vulnerabilities exceeding the threshold of 1 occurrence/minute. Meanwhile, the "Alert grouping" feature on Grafana was configured to aggregate information before sending it via Amazon SNS, helping the team react quickly while preserving the 1,000 free email limit of AWS.

### 4. Information Security Team (DevSecOps) – Integrating Security from the Design Phase
*   **Challenges:** During the information security assessment phase, the OWASP ZAP tool initially returned many False Positives. The Backend source code still possessed risks due to storing the DB password and JWT Secret in the configuration file. However, migrating to Cloud environment variables caused the Fargate container to fail during initialization.
*   **Solutions:** The team applied the "Shift-left Security" approach – introducing security elements right from the design phase. All sensitive information was removed from the source code and centrally managed in the AWS Systems Manager Parameter Store. To fix the Task crash error, the `ssm:GetParameters` permission was added to the execution IAM Role. At the network edge, the AWS WAF firewall was deployed in two layers: protecting the interface on CloudFront and protecting the API traffic on the ALB. Coordinated with the SonarCloud static code scanning tool, risks were analyzed into specific guidelines (such as applying `encodeURIComponent`) so the development team could resolve them promptly.

---

## IV. Conclusion and the Journey Ahead

The process of migrating "Mini Social Network" to the Cloud environment helped the team solve the puzzle of balancing cost optimization, automation capabilities, and end-user experience.

However, the architecture in the current diagram is not yet the final version. To ensure the system achieves the highest level of security, the project is entering a rigorous evaluation phase: Code Freeze & Security Audit. The entire architecture will undergo a comprehensive security review before we officially finalize the "Final Architecture".

## V. Architecture Diagrams of the "Mini Social Network" Project Before and After

<h4 align="center"><em>Initial implemented architecture diagram</em></h4>

![Initial implemented architecture diagram](anh1.png)

<h4 align="center"><em>Architecture diagram after feedback and cost optimization</em></h4>

![Architecture diagram after feedback and cost optimization](anh2.png)
> Blog on AWS Study Group: Blog post link https://www.facebook.com/groups/awsstudygroupfcj/permalink/2198727654225528
<br>
> We look forward to receiving feedback, evaluations, and shared experiences from the experts and peers in the AWS Study Group VN!