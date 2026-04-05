---
title: "Event 3"
date: 2026-01-29
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

## Summary Report: "AWS re:Invent 2025 – App Modernization & GenAI Architecture"

### Event Objectives

- Review key announcements from AWS re:Invent 2025 (Nova models, Trainium3 UltraServers, AI agents, GenAI, modernization, data...).
- Share best practices for application modernization, microservices architecture, event-driven systems, serverless/container compute, and AI-driven development.
- Create networking opportunities between AWS experts, partners, and the cloud/AI community in Vietnam.

### Speakers

- **AWS speakers**: Solution Architects and Specialists from AWS Vietnam sharing modern architecture, GenAI, and real-world deployment experience.
- **Customer/Partner speakers**: Representatives from Vietnamese enterprises and AWS partners sharing case studies on transitioning from legacy monolith to microservices and applying event-driven AI on AWS.

### Key Highlights

#### Legacy Architecture Drawbacks

- Monolithic applications are hard to scale per module; every release requires building and deploying the full system, increasing risk and downtime.
- Technology lock-in makes it difficult to adopt new technologies like serverless, containers, GenAI, and real-time data processing.
- Low fault tolerance — a single failure can affect the entire system; blue/green and canary deployments are hard to implement.

#### Microservices Architecture

- Split applications into small, independent services that can be scaled and deployed separately; enables faster CI/CD.
- Allows technology choice per service (polyglot architecture); easier to integrate AI, streaming, and event-driven patterns.
- On AWS: typically combines Amazon ECS/EKS/Lambda, API Gateway, Service Discovery, and observability stack (CloudWatch, X-Ray).

#### Event-Driven Architecture

- Using events for loose coupling between services makes the system flexible and easy to extend.
- On AWS: Amazon EventBridge, SNS/SQS, Kinesis for real-time analytics and multi-domain integration.
- Well-suited for complex business processes (orders, payments, notifications, audit logs) and streaming data.

#### Compute Evolution

- Journey from traditional EC2 to containers (ECS/EKS), serverless (Lambda, Fargate), and AI-optimized instances like Trainium3 UltraServers.
- Goal: optimize cost, auto-scaling, and reduce operational overhead so teams focus on business logic.

#### Amazon Q Developer

- AI assistant for developers integrated into IDE and AWS console; helps generate code, refactor, write tests, and suggest architectures.
- Accelerates modernization by analyzing legacy code, proposing migration paths, and automating infrastructure as code tasks.

### Key Takeaways

- **Cloud-native design first**: Prioritize decoupling, elasticity, fault-tolerance, automation rather than simple lift-and-shift.
- **Domain-Driven Design**: Clearly define bounded contexts before moving to microservices and event-driven patterns.
- **Hybrid architecture**: Microservices + event-driven + serverless/containers + managed data services (Aurora, DynamoDB, streaming, vector DB).
- **Resilience patterns**: Circuit breaker, retry, backoff, idempotency; end-to-end observability and security by design.
- **Phased migration**: Use blue/green deployments and feature flags to reduce risk when migrating incrementally rather than big-bang rewrites.

### Applying to Work

- Apply decomposition thinking: break monolith into clear domains, propose microservices or modular monolith architecture.
- Choose appropriate AWS services (API Gateway + Lambda for POC, ECS/EKS for production); add event-driven communication with SQS/EventBridge.
- Begin using Amazon Q Developer in the development workflow to assist with code writing, testing, and refactoring.

### Event Photos

**Full venue view and opening session**

![Full venue and opening session](/images/3-EventParticipated/3.3-Event3/reInvent_RECAP_1.jpg)

**Check-in Session #1**

![Check-in Session 1](/images/3-EventParticipated/3.3-Event3/reInvent_RECAP_2.jpg)

**Check-in Session #2**

![Check-in Session 2](/images/3-EventParticipated/3.3-Event3/reInvent_RECAP_3.jpg)

**AWS keynote: Machine Learning & AI Innovation #1**

![AWS ML & AI Innovation keynote 1](/images/3-EventParticipated/3.3-Event3/reInvent_RECAP_4.jpg)

**AWS keynote: Machine Learning & AI Innovation #2**

![AWS ML & AI Innovation keynote 2](/images/3-EventParticipated/3.3-Event3/reInvent_RECAP_5.jpg)

**New Year at AWS — ready for new challenges and milestones**

![New year smiles at AWS](/images/3-EventParticipated/3.3-Event3/reInvent_RECAP_6.jpg)

**Team photo and event closing**

![Team photo at event closing](/images/3-EventParticipated/3.3-Event3/reInvent_RECAP_7.jpg)

---

## Summary

Overall, the event emphasized the importance of modern architectural thinking, practical migration strategies, and the role of AWS services in building scalable, secure, and AI-capable applications.
