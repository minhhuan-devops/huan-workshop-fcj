---
title : "Verify Data & Messaging"
date : 2024-01-01 
weight : 3
chapter : false
pre : " <b> 4.3. </b> "
---

#### Verify Data and Queues

After the `terraform apply` command has completed successfully, all internal services are provisioned. In this step, we will verify the infrastructure on AWS:

1. **Amazon RDS (MySQL):** Check if the `auth`, `event`, `ticket` databases have been created successfully.
   - Access the AWS Console, enter **RDS** in the search bar, and select the **RDS** service.
   
   ![Search for RDS](image-1.png)
   
   - Select **Databases** from the left-hand menu.
   
   ![Select RDS Databases](image.png)
   
   - Confirm that the databases have been successfully created and are in the **Available** state.
   
   ![Confirm RDS success](image-2.png)

2. **Amazon ElastiCache (Redis):** Verify the Redis endpoint and connectivity.
   - Enter **ElastiCache** in the search bar and select the **ElastiCache** service.
   
   ![Search for Redis](image-3.png)
   
   - Select **Redis clusters** to view the list of your provisioned nodes.
   
   ![Select Redis clusters](image-4.png)
   
   - Confirm that the Redis cluster is provisioned and shows an **Available** status.
   
   ![Confirm Redis success](image-5.png)

3. **Amazon SQS:** Ensure your SQS queues are ready to receive events.
   - Enter **SQS** in the search bar and select **Simple Queue Service**.
   
   ![Search for SQS](image-6.png)
   
   - Confirm that your SQS queues have been correctly listed in the console.
   
   ![Confirm SQS success](image-7.png)