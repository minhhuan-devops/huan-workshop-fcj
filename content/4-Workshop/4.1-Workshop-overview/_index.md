---
title : "Introduction"
date : 2024-01-01 
weight : 1 
chapter : false
pre : " <b> 4.1. </b> "
---

#### Architecture Overview

The **FPT Event Management System** leverages a modern, event-driven microservices architecture on AWS. It is designed to handle high-traffic flash sales securely and efficiently.

+ **Decoupled domains:** The system is divided into bounded contexts (Auth, Event, Ticket, Staff, Venue), isolated as stateless microservices running on Amazon ECS.
+ **Security & Edge:** Amazon CloudFront caches frontend assets while AWS WAF defends against web exploits. Internal workloads reside in Private Subnets, accessible only via API Gateway and an Application Load Balancer (ALB).
+ **Event-Driven Processing:** An Amazon SQS queue handles background workloads like sending ticket PDFs through Amazon SES via the Notification Service, preventing synchronous timeouts.
+ **Robust Data Tier:** Relational states are managed by an Amazon RDS MySQL Multi-AZ cluster, complemented by Amazon ElastiCache (Redis) to offload frequent read requests. 

#### Workshop Outline

In this workshop, you will deploy the entire architecture via Infrastructure as Code (Terraform) and then verify components sequentially:
+ **Deployment:** Provision the AWS infrastructure components fully automated via Terraform.
+ **Verify Data & Messaging:** Inspect and validate local connectivity to RDS, ElastiCache, SQS queues, and SES integrations.
+ **Verify Backend & Networking:** Test internal APIs via the Application Load Balancer and ensure microservices are successfully running on ECS Fargate.
+ **Verify Frontend & Edge:** Access the fully functional React frontend distributed globally via CloudFront and secure traffic through AWS WAF.

![FPT Event Management Architecture](/images/2-Proposal/fpt-event-management.jpg)