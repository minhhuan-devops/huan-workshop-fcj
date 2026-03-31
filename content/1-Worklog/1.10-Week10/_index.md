---
title: "Week 10 Worklog"
date: 2026-03-09
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

* Understand Amazon CloudFront as a global Content Delivery Network (CDN).
* Configure Origins, Behaviors, Cache Policies, and Origin Access Control (OAC).
* Secure and optimize content delivery for static assets and dynamic APIs.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 (Mon) | - Introduction to CloudFront: edge locations, Points of Presence (PoPs), regional edge caches <br> - Learn CloudFront components: Distributions, Origins, Behaviors, Cache Policies, TTL | 03/09/2026 | 03/09/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 (Tue) | - **Practice:** <br>&emsp; + Create a CloudFront distribution with S3 origin <br>&emsp; + Configure Origin Access Control (OAC) to block direct S3 access <br>&emsp; + Update S3 bucket policy for CloudFront-only access | 03/10/2026 | 03/10/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 (Wed) | - Learn CloudFront Behaviors: path patterns, cache policies, origin request policies <br> - Configure multiple behaviors: <br>&emsp; + `/api/*` → ALB/API Gateway origin (no cache) <br>&emsp; + `/*` → S3 origin (cache static assets) | 03/11/2026 | 03/11/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 (Thu) | - Learn CloudFront security: HTTPS enforcement, custom SSL certificates (ACM), Geo Restriction <br> - Study CloudFront Functions vs Lambda@Edge use cases <br> - **Practice:** Configure HTTPS redirect and attach ACM certificate | 03/12/2026 | 03/12/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 (Fri) | - Learn CloudFront cache invalidation and monitoring (Cache Hit Rate, 4xx/5xx error rates) <br> - **Practice:** <br>&emsp; + Invalidate a path pattern after code deployment <br>&emsp; + Review CloudWatch metrics and access logs for the distribution | 03/13/2026 | 03/13/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Week 10 Achievements:

* Understood CloudFront edge architecture and how PoPs reduce latency for end users globally.
* Created a CloudFront distribution with S3 origin secured by Origin Access Control (OAC).
* Configured multi-behavior routing: static assets from S3 (cached) and API from ALB (uncached).
* Enforced HTTPS-only access and attached an ACM SSL certificate to the distribution.
* Performed cache invalidation after a deployment and monitored Cache Hit Ratio in CloudWatch.
* Understood when to use CloudFront Functions vs Lambda@Edge based on execution context.
* ...
