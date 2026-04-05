---
title : "Verify Data & Messaging"
date : 2024-01-01 
weight : 3
chapter : false
pre : " <b> 4.3. </b> "
---

#### Verify Data and Queues

After the `terraform apply` command completes, all internal services are provisioned. In this step, we navigate to the AWS Console to verify each service one by one.

---

### 1. Amazon RDS (MySQL)

Amazon RDS is a fully managed relational database service — no server provisioning or patching required. It provides a standard MySQL database with automated backups and high availability built in.

**Check that the `auth`, `event`, `ticket`,... databases have been created successfully:**

- Enter **RDS** in the search bar and select the **RDS** service.

![Search for RDS](/4-workshop/4.3-verify-data-messaging/image-1.png)

- Select **Databases** from the left-hand menu.

![Select RDS Databases](/4-workshop/4.3-verify-data-messaging/image.png)

- Confirm all databases are created and show an **Available** status.

![Confirm RDS success](/4-workshop/4.3-verify-data-messaging/image-2.png)

---

### 2. Amazon ElastiCache (Redis)

Amazon ElastiCache is a high-speed, fully managed caching service. It temporarily stores frequently accessed data to reduce the load on RDS and returns responses in milliseconds.

**Verify the Redis cluster is provisioned:**

- Enter **ElastiCache** in the search bar and select the **ElastiCache** service.

![Search for ElastiCache](/4-workshop/4.3-verify-data-messaging/image-3.png)

- Select **Redis clusters** from the left-hand menu.

![Select Redis clusters](/4-workshop/4.3-verify-data-messaging/image-4.png)

- Confirm the Redis cluster is created and shows an **Available** status.

![Confirm Redis success](/4-workshop/4.3-verify-data-messaging/image-5.png)

---

### 3. Amazon SQS

Amazon SQS (Simple Queue Service) enables asynchronous communication between microservices. When the Ticket Service completes a transaction, it pushes an event to SQS and the Notification Service picks it up to send an email — they never block each other.

**Ensure the queues are ready to receive events:**

- Enter **SQS** in the search bar and select **Simple Queue Service**.

![Search for SQS](/4-workshop/4.3-verify-data-messaging/image-6.png)

- Confirm that your SQS queues are listed correctly in the console.

![Confirm SQS success](/4-workshop/4.3-verify-data-messaging/image-7.png)