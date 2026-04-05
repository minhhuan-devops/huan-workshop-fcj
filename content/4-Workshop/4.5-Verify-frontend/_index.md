---
title : "Verify Frontend & API Gateway"
date : 2024-01-01 
weight : 5
chapter : false
pre : " <b> 4.5. </b> "
---

#### Verify User Interface and API Gateway

The final step is to check the Public Facing components that allow end users (those outside our VPC) to interact with the system.

1. **Verify Amazon API Gateway:**
   - Acting as our public gateway, we need to ensure its routes are correctly proxying traffic internally to the ALB.
   - Access **API Gateway** from the search bar.
   
   ![Search for API Gateway](image.png)
   
   - Select the deployed API (e.g., `fpt-event-api`).
   
   ![Select the fpt-event-api](image-1.png)
   
   - Verify that all necessary routes have been linked properly.
   
   ![Verify API routes](image-2.png)

2. **Verify Amazon S3 & CloudFront:**
   - CloudFront serves the static React frontend hosted on S3. You can access the interface via the CloudFront Distribution URL.
   - Navigate to the **CloudFront** service.
   
   ![Search for CloudFront](image-6.png)
   
   - Select the **Distributions** menu.
   
   ![Select Distributions](image-7.png)
   
   - Copy the **Distribution domain name** and navigate to it in a browser window.
   
   ![Get the CloudFront URL](image-8.png)
   
   - The ReactJS interface should load successfully if the deployment was successful.
   
   ![ReactJS Interface success](image-3.png)

3. **Verify AWS WAF (Web Application Firewall):**
   - Ensure the security rules are in place through WAF Web ACLs to prevent malicious attacks.
   - Navigate to **WAF & Shield**, select **Web ACLs**, and confirm that the firewall is attached to the CloudFront distribution.
   
   ![WAF page](image-4.png)
   
   ![Confirm WAF Configuration](image-5.png)
