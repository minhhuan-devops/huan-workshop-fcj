---
title : "Verify Frontend & API Gateway"
date : 2024-01-01 
weight : 5
chapter : false
pre : " <b> 4.5. </b> "
---

#### Verify the User Interface and API Gateway

This step validates the Public Facing components — the parts that end users outside the VPC network can interact with.

---

### 1. Amazon API Gateway

Amazon API Gateway is the single secure entry point that handles all API calls from the internet into the backend system. It enforces rate limiting, security policies, and routes each request to the correct internal microservice.

**Verify that all Routes are configured correctly:**

- Enter **API Gateway** in the search bar and select the service.

![Search for API Gateway](/4-workshop/4.5-verify-frontend/image.png)

- Select the deployed API (e.g., `fpt-event-api`).

![Select fpt-event-api](/4-workshop/4.5-verify-frontend/image-1.png)

- Review the Routes to confirm they are fully configured to point to the internal microservices.

![Check API Gateway Routes](/4-workshop/4.5-verify-frontend/image-2.png)

---

### 2. Amazon S3 & CloudFront

Amazon S3 is an object storage service used to host the static ReactJS frontend files. Amazon CloudFront is a global Content Delivery Network (CDN) — it caches static assets from S3 at edge locations close to end users, dramatically improving page load speed.

**Get the CloudFront URL to access the website:**

- Enter **CloudFront** in the search bar and select the service.

![Search for CloudFront](/4-workshop/4.5-verify-frontend/image-6.png)

- Select **Distributions** from the left-hand menu.

![Select Distributions](/4-workshop/4.5-verify-frontend/image-7.png)

- Copy the **Distribution domain name** and open it in a browser to access the website.

![Get CloudFront Domain Name](/4-workshop/4.5-verify-frontend/image-8.png)

- A successfully rendered ReactJS interface confirms the entire system is working correctly.

![ReactJS website interface](/4-workshop/4.5-verify-frontend/image-3.png)

---

### 3. AWS WAF (Web Application Firewall)

AWS WAF is a web application firewall that detects and blocks malicious traffic — such as SQL Injection and XSS attacks — at the CloudFront layer before they ever reach the backend.

**Confirm WAF is attached to CloudFront:**

- Enter **WAF & Shield** in the search bar and select **Web ACLs**.

![WAF & Shield page](/4-workshop/4.5-verify-frontend/image-4.png)

- Confirm the Web ACL is created and correctly associated with your CloudFront Distribution.

![Confirm WAF configuration on CloudFront](/4-workshop/4.5-verify-frontend/image-5.png)
