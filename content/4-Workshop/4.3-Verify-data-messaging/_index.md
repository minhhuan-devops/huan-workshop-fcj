---
title : "Verify Data & Messaging"
date : 2024-01-01 
weight : 3
chapter : false
pre : " <b> 4.3. </b> "
---

#### Verify Data and Queues

After running `terraform apply`, all internal services have been provisioned. In this step, we will connect to our internal environment to verify:

1. **Amazon RDS (MySQL):** Check if the databases (`auth`, `event`, `ticket`, etc.) were initialized successfully.
2. **Amazon ElastiCache (Redis):** Validate the Redis endpoint and its connectivity.
3. **Amazon SQS & SES:** Ensure the SQS queue is ready to accept event messages, and the SES sender email is verified.

You can provision a temporary EC2 Bastion Host or use AWS Systems Manager (Session Manager) to access the Private Subnet and perform these verifications.