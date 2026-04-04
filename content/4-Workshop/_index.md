---
title: "Workshop"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 4. </b> "
---

# FPT Event Management System on AWS

![FPT Event Management Architecture](/images/2-Proposal/fpt-event-management.jpg)

#### Overview

**FPT Event Management System** provides a comprehensive, highly scalable platform for managing events, issuing tickets, allocating staff, and maintaining venues using an AWS Microservices architecture.

In this workshop, you will learn how to build, configure, and deploy a robust event management platform utilizing AWS managed services to ensure high availability, security, and scalability during massive flash sales.

The architecture implements a containerized microservices model:
+ **Frontend** - Hosted on Amazon S3 and distributed globally via Amazon CloudFront, protected by AWS WAF.
+ **API Routing** - Securely routes incoming traffic using Amazon Route 53, API Gateway, and an Application Load Balancer (ALB).
+ **Service Layer** - Domain-specific backend microservices (Auth, Event, Ticket, Staff, Venue, Notification) orchestrated by Amazon ECS.
+ **Event-Driven Messaging** - Amazon SQS buffers workload queues while Amazon SES handles asynchronous email dispatch.
+ **Data Layer** - Amazon RDS (MySQL 8.0 Multi-AZ) for durable transactional data and Amazon ElastiCache (Redis) for high-performance caching.
+ **Monitoring & Storage** - Amazon CloudWatch for centralized logging and Amazon S3 for durable object storage.

#### Content

1. [Workshop overview](4.1-Workshop-overview/)
2. [Prerequisites & Deployment](4.2-Prerequisite-and-deployment/)
3. [Verify Data & Messaging (RDS, Redis, SQS, SES)](4.3-Verify-data-messaging/)
4. [Verify Backend Microservices (ECS, ALB)](4.4-Verify-backend/)
5. [Verify Frontend & API Gateway (S3, CloudFront, WAF, API Gateway)](4.5-Verify-frontend/)
6. [Clean up](4.6-Cleanup/)