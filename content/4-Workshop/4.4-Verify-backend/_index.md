---
title : "Verify Backend Microservices"
date : 2024-01-01 
weight : 4
chapter : false
pre : " <b> 4.4. </b> "
---

#### Verify ECS Services Running on Fargate

The system's microservices operate inside a private subnet and communicate with each other through an internal Application Load Balancer (ALB) — they are never exposed directly to the public internet.

---

### 1. Amazon ECS (Elastic Container Service)

Amazon ECS is a container orchestration service for managing Docker containers. Combined with AWS Fargate (a serverless compute engine), you do not need to manage any underlying EC2 instances — AWS automatically provisions the right amount of CPU and RAM for each container.

**Check the status of ECS Clusters and Services:**

- Enter **ECS** in the search bar and select **Elastic Container Service**.

![Search for ECS](/4-workshop/4.4-verify-backend/image.png)

- Select your Cluster and review the list of services (`auth-service`, `event-service`, `ticket-service`, `venue-service`, `notification-service`).

![List of ECS Services](/4-workshop/4.4-verify-backend/image-1.png)

- Confirm all services are in an **Active** state.

![ECS Service Active state](/4-workshop/4.4-verify-backend/image-2.png)

- Verify the **Running Tasks** count matches your desired configuration.

![Running Tasks count](/4-workshop/4.4-verify-backend/image-3.png)

---

### 2. Application Load Balancer (ALB) & Target Groups

The Application Load Balancer is an intelligent traffic distributor — it receives requests from the API Gateway and forwards them to the appropriate available backend container. Target Groups define which set of containers receives traffic from each route.

**Verify that Target Groups are in a Healthy state:**

- Enter **EC2** in the search bar and navigate to the **EC2 Console**.

![Search for EC2 Console](/4-workshop/4.4-verify-backend/image-4.png)

- In the left menu, scroll down to **Load Balancing** and select **Load Balancers**.

![Select Load Balancers](/4-workshop/4.4-verify-backend/image-5.png)

- Select the internal ALB (e.g., `fpt-event-alb`).

![Select internal ALB](/4-workshop/4.4-verify-backend/image-6.png)

- Open the **Listeners and rules** tab to review routing configurations.

![Listeners and Rules tab](/4-workshop/4.4-verify-backend/image-7.png)

- Navigate to **Target Groups** (left menu, below Load Balancers) and confirm all containers pass the Health Check showing a **Healthy** status.

![Target Groups Healthy status](/4-workshop/4.4-verify-backend/image-8.png)

![Target Group Health Check detail](/4-workshop/4.4-verify-backend/image-9.png)
