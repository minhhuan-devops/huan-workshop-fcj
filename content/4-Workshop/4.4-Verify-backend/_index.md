---
title : "Verify Backend Microservices"
date : 2024-01-01 
weight : 4
chapter : false
pre : " <b> 4.4. </b> "
---

#### Verify ECS Services running on AWS Fargate

Our microservices are not publicly accessible over the internet but rather run in a private subnet, behind an internal Application Load Balancer (ALB).

1. **Verify ECS Clusters and Services Status:**
   - Access the **Amazon ECS Console** from the AWS search bar.
   
   ![Search for ECS](image.png)
   
   - Select the deployed Cluster and navigate to the Services tab to see the list of backend instances (`auth-service`, `event-service`, `ticket-service`, `venue-service`, `notification-service`).
   
   ![ECS Services list](image-1.png)
   
   - Ensure all services have been deployed successfully and show **Active** status.
   
   ![Service deployment status](image-2.png)
   
   - Verify that the number of **Running Tasks** matches the desired configuration deployed by Terraform.
   
   ![Check Running Tasks](image-3.png)

2. **Verify Target Groups on the Application Load Balancer:**
   - To verify container routing, go to the **EC2 Console**.
   
   ![Search for EC2](image-4.png)
   
   - Scroll down the left menu to the **Load Balancing** section and select **Load Balancers**.
   
   ![Select Load Balancers](image-5.png)
   
   - Click on the internal ALB provisioned for our system (e.g., `fpt-event-alb`).
   
   ![Select the internal ALB](image-6.png)
   
   - Switch to the **Listeners and rules** tab to verify that the routing rules are configured correctly.
   
   ![Check Listeners and Rules](image-7.png)
   
   - Next, go to **Target Groups** (located in the left menu under Load Balancers), select each group and ensure that the backend containers pass the Health Checks and report a **Healthy** status.
   
   ![Healthy Target Groups status](image-8.png)
