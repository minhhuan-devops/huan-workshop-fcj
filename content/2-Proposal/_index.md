---
title: "Proposal"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# FPT Event Management System  
## AWS Microservices-based Event Management and Ticketing Solution

### 1. Executive Summary  
The **FPT Event Management** system is designed to provide a comprehensive, highly scalable platform for managing events, issuing tickets, allocating staff, and maintaining venues. Employing an AWS Microservices architecture (via Amazon ECS), the system ensures high availability during massive flash sales, optimizes asynchronous notification delivery, and strictly enforces security from the network layer up to the data layer.

### 2. Problem Statement  
**Current Issues** For large-scale events, flash ticket sales typically generate massive traffic spikes. Traditional monolithic systems are prone to overload, database bottlenecks, and face difficulties when scaling specific features. Additionally, sending notifications (e-tickets, event reminders) synchronously drastically slows down the system's responsiveness.

**Solution** We implement a Microservices architecture to isolate business domains contextually: **Auth, Event, Ticket, Staff**, and **Venue**. All Backend services are containerized (Docker) and orchestrated by **Amazon ECS**. The Frontend is hosted on **Amazon S3** and distributed globally via **CloudFront CDN** along with **AWS WAF** to block malicious web attacks. API requests are centrally routed through **API Gateway** and load-balanced by an **ALB (Application Load Balancer)** to the ECS cluster. Notification delivery is offloaded to a dedicated **Notification Service** which handles tasks asynchronously using **Amazon SQS** as a message queue and **Amazon SES** for dispatching emails. Crucial relational data is durably stored in **Amazon RDS (MySQL 8.0 Multi-AZ)**, while **ElastiCache (Redis)** serves as a robust caching layer for blazing-fast data retrieval.

**Benefits and ROI** - **Scalability:** The 'Ticket' service can be scaled horizontally independently during flash sales, preserving the stability of other services.
- **High Availability:** Leveraging RDS Multi-AZ and a containerized architectural model ensures near-zero downtime.
- **Improved User Experience:** Fast load times supported by CloudFront, ensuring smooth, uninterrupted access.
- While it demands an upfront investment in infrastructure setup, the Microservices approach yields long-term efficiencies and drastically mitigates the financial risks associated with system outages.

**Event Lifecycle** The system covers the full lifecycle of an event:
- **Organizer:** Submits an event request and books the venue area.
- **Admin:** Approves the request and opens ticket sales.
- **Student:** Purchases tickets using an e-Wallet or VNPay.
- **System:** Automatically issues a PDF ticket with a QR code and dispatches a notification email.
- **Staff:** Scans the QR code at the check-in counter, which automatically updates attendance reports.

**Design Targets** - **High data integrity:** Strictly enforced for payment scenarios and the ticket issuance flow.
- **Good concurrency behavior:** Evaluated to ensure the system withstands high traffic comfortably during simultaneous ticket purchases.
- **Low storage waste & clear operational ownership:** Minimizing unused storage allocations and distinctly demarcating service administration among teams.

### 3. Solution Architecture  
The system harnesses AWS Managed Services alongside defense-in-depth networking layers and asynchronous event-handling to eliminate high-latency bottlenecks.

![FPT Event Management Architecture](/images/2-Proposal/fpt-event-management.jpg)

**Utilized AWS Services** - **Amazon Route 53 & CloudFront**: DNS routing alongside CDN distribution guarantees that static Frontend assets (hosted on **S3**) are globally cached and delivered with minimal latency.
- **AWS WAF**: Web Application Firewall safeguarding against prevalent exploits (e.g., SQL Injection, XSS) and applying rigid Rate Limiting.
- **Amazon API Gateway & ALB**: Absorbs all inbound API calls, securely routing them through the Load Balancer to the backend ECS cluster.
- **Amazon ECS (Elastic Container Service)**: Hosts and coordinates the lifecycles of the Microservices (Auth, Ticket, Event, Staff, Venue, Notification).
- **Amazon RDS (MySQL 8.0 Multi-AZ) & ElastiCache (Redis)**: Form the data and caching layer; RDS ensures durable transactional storage while Redis slashes querying times.
- **Amazon SQS & Amazon SES**: Powers the Event-Driven architecture; SQS buffers workload queues, and SES facilitates automated email outreach.
- **Amazon S3 (Storage)**: A highly durable object storage holding event media assets and PDF invoices.
- **Amazon CloudWatch**: Gathers aggregated metrics, central logs, and performance oversight for the entirety of the architecture.

### 4. Technical Implementation  
**Deployment Phases** 1. **Design & Provisioning (IaC):** Blueprints of the Database structure and VPC topology are codified. Infrastructure as Code via Terraform or AWS CDK provisions the VPC, ECS Clusters, ALB, and RDS automatically.
2. **Microservices Development:** Dividing the monolithic codebase into domain-specific repositories for Frontend and respective Backend Services, including respective Dockerfiles.
3. **CI/CD Pipeline Setup:** GitHub Actions will trigger on code pushes to construct Docker Images, push them to ECR, and deploy newer task definitions directly to ECS.
4. **Integration & Load Testing:** Linking the frontend to the API Gateway. Load testing tools will simulate intense ticket sales, verifying WAF thresholds and validating Auto-Scaling mechanisms across ECS and ElastiCache.

**Technical Requirements** - **Frontend**: Built with the **ReactJS** library using a Static Export strategy, enabling robust hosting explicitly on S3.
- **Backend Services**: Developed using the **Golang** programming language. Container artifacts must adhere to Stateless principles for optimal orchestration maneuverability.
- **Security Posture**: Intra-VPC communications are barred from exposure to the public internet network. RDS and ElastiCache strictly reside within Private Subnets.

### 5. DevSecOps Strategy and Security Testing Process
The system applies a Shift-Left Security mindset, integrating information security checks right from the coding phase up to cloud deployment. The project team is clearly divided into 3 independent roles to ensure objectivity: Developer (Dev), Infrastructure Administrator (DevOps), and Penetration Tester (Pentester).

The DevSecOps process is divided into 3 core phases:

* **Phase 1: Local Application Pentest:**
    * Conduct static code analysis and Dynamic Application Security Testing (DAST) on the local Docker environment.
    * Focus on detecting business logic flaws, weak authentication, and internal network misconfigurations according to the OWASP Top 10 standards.
* **Phase 1.5: Remediation & Secure Coding:**
    * The Developer (Dev) receives the security report and remediates vulnerabilities directly at the source code level.
    * Apply security standards such as the Bcrypt hashing algorithm, JWT protection via HttpOnly Cookies, and internal authentication mechanisms (Internal Token) for Microservices.
* **Phase 2: Cloud Infrastructure Pentest:**
    * Perform security assessment after DevOps deploys the system to AWS using Terraform (IaC).
    * Focus on perimeter security auditing: Review Amazon VPC network configurations, tighten Security Groups for Amazon RDS, eliminate Bastion Hosts, and establish Rate Limiting on AWS WAF/CloudFront to prevent Economic Denial of Sustainability (EDoS) attacks.

### 6. Roadmap & Milestones  
- **Month 1**: Conduct comprehensive surveys, finalize detailed Data Models, code IaC scripts mimicking VPC, Database tiers, and fundamental networking.
- **Month 2**: Build and deploy the static Frontend stack onto S3 + CloudFront. Proceed with building out core ECS backend services (Auth, Event, Ticket). **Conduct Phase 1 Pentest on the local environment and Phase 1.5 Source Code Remediation**.
- **Month 3**: Finalize peripheral services (Venue, Staff), configure SQS + SES notifications, and integrate the entire system via API Gateway. **Perform Phase 2 Pentest to audit AWS infrastructure (Cloud Security).** Execute Load Testing and launch to Production.

### 7. Budget Estimation
**Infrastructure Costing**
- Compute (Amazon ECS with Fargate): $35.00/month (Estimated for minimum 6 microservices).
- Database (Amazon RDS MySQL Multi-AZ): $34.00/month (db.t3.micro).
- Caching (Amazon ElastiCache Redis): $12.00/month (cache.t3.micro).
- Networking (ALB, API Gateway, CloudFront, Route53): $20.00/month.
- Web Security (AWS WAF): $6.00/month (1 foundational Web ACL).
- Storage & Messaging (S3, SQS, SES, CloudWatch): $2.00/month.

**Total:** $109.00/month, $1,308.00 annually

### 8. Risk Assessment
**Risk Matrix**
- Microservices data inconsistency: High Impact, Medium Probability.
- Localized payment flow overload: High Impact, Low Probability.
- Runaway AWS operational costs: Medium Impact, Low Probability.
- Leakage of sensitive information/passwords in Infrastructure as Code (IaC): Very High Impact, Medium Probability.
- Economic Denial of Sustainability (EDoS) attacks via virtual traffic: High Impact, Medium Probability.

**Mitigation Strategy**
- Data Inconsistency: Establish Saga Patterns or Event-driven propagation architectures supported by SQS.
- Checkout Bottleneck: Apply asynchronous queue ingest logic and highly responsive Auto-scaling metrics.
- Budgeting: Configure strict AWS Budget thresholds with associated billing alarms and enforce absolute max-capacity limitations.
- Configuration Security: Absolutely no hardcoded passwords; integrate AWS Secrets Manager into the CI/CD pipeline.
- EDoS Prevention: Apply micro-segmentation for Security Groups and configure Targeted Rate Limiting on AWS WAF.

**Contingency Plan**
- Immediately regress to manual administrative ticket validation flows and check-in procedures if sweeping infrastructural downtime strikes.
- Reinstate stable prior cloud footprints via Terraform (IaC) configuration templates to recover environments rapidly.

### 9. Expected Outcomes
**Technical Innovations:** Completely automate the ticket issuance footprint and financial gateways, effortlessly withstanding dense ticket purchasing frenzies.
**Long-Term Value Extrapolation:** Solidify a rigorous core framework that remains easy to maintain, establishing a foundation to eventually repackage this ecosystem as a modular SaaS platform for future FPT engagements.