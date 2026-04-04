---
title : "Verify Backend Microservices"
date : 2024-01-01 
weight : 4
chapter : false
pre : " <b> 4.4. </b> "
---

#### Verify ECS Fargate Services

Our microservices are not exposed directly to the internet; they reside securely behind an internal Application Load Balancer (ALB).

1. Go to the **Amazon ECS Console**.
2. Verify the status of your Clusters and individual Services (`auth-service`, `event-service`, `ticket-service`, `notification-service`).
3. Ensure the number of **Running Tasks** matches your Terraform configurations.
4. Navigate to the **Target Groups** in the EC2 Console to verify that all containers are passing their Health Checks (**Healthy** status).
5. Attempt a test API call against the Internal ALB DNS (using `curl` from a Bastion host).
