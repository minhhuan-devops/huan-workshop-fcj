---
title : "Verify Frontend & API Gateway"
date : 2024-01-01 
weight : 5
chapter : false
pre : " <b> 4.5. </b> "
---

#### Verify User Interface and API Gateway

The final verification step handles our public-facing infrastructure that end-users interact with.

1. **Amazon API Gateway:** Verify the deployed routes that proxy requests to the internal ALB. Send a test request to the public API Gateway endpoint to fetch event data.
2. **Amazon S3 & CloudFront:** Retrieve the CloudFront Distribution URL from the Terraform outputs. Visit the URL in your web browser to load the ReactJS frontend.
3. **AWS WAF:** Simulate a malicious request (e.g., adding an SQL injection pattern like `?id=1' OR '1'='1`) to the CloudFront URL and confirm that WAF blocks the request by returning a HTTP 403 Forbidden.
