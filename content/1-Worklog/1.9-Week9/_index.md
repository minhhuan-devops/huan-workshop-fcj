---
title: "Week 9 Worklog"
date: 2026-03-02
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Configure API Gateway integrations: Lambda, HTTP, AWS Service, and VPC Link.
* Implement Lambda Authorizers and Cognito User Pools for API authentication.
* Connect API Gateway to private backend services via VPC Link and NLB.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 (Mon) | - Review API Gateway integration types: Lambda Proxy, Lambda Custom, HTTP, AWS Service, Mock <br> - Understand Proxy vs Non-Proxy integration differences (headers, body, status codes) | 03/02/2026 | 03/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 (Tue) | - **Practice:** <br>&emsp; + Create a Lambda function (Python/Node.js) <br>&emsp; + Integrate with API Gateway using Lambda Proxy integration <br>&emsp; + Test end-to-end: API GW → Lambda → response | 03/03/2026 | 03/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 (Wed) | - Learn API Gateway authorizers: Lambda Authorizer (token/request type) vs Cognito Authorizer <br> - **Practice:** <br>&emsp; + Create a Lambda Authorizer (bearer token validation) <br>&emsp; + Attach to API endpoint and test with/without valid token | 03/04/2026 | 03/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 (Thu) | - Learn VPC Link: connecting API Gateway to private backend (NLB in VPC) <br> - **Practice:** <br>&emsp; + Create a VPC Link targeting an existing NLB <br>&emsp; + Configure HTTP_PROXY integration via VPC Link <br>&emsp; + Verify private ECS/EC2 service traffic through API GW | 03/05/2026 | 03/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 (Fri) | - Learn API Gateway caching: TTL, cache invalidation, per-key caching <br> - Study X-Ray tracing integration for API Gateway <br> - **Practice:** Enable caching on a GET endpoint and measure response time improvement | 03/06/2026 | 03/06/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Week 9 Achievements:

* Integrated API Gateway with a Lambda function using Lambda Proxy integration end-to-end.
* Implemented a custom Lambda Authorizer to validate bearer tokens on protected routes.
* Created a VPC Link and connected API Gateway to a private NLB-backed service.
* Verified that API Gateway correctly forwards requests to private ECS containers via VPC Link.
* Enabled API Gateway response caching and observed significant latency reduction.
* Activated AWS X-Ray tracing and analyzed the service map for the API → Lambda call chain.
* ...
