---
title: "Week 8 Worklog"
date: 2026-02-23
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Understand Amazon API Gateway and the differences between REST API and HTTP API.
* Configure endpoints, methods, stages, and deployment settings.
* Secure APIs with API keys, usage plans, and resource policies.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 (Mon) | - Introduction to API Gateway: REST API vs HTTP API vs WebSocket API <br> - Learn core concepts: Resources, Methods, Stages, Deployments, Throttling <br> - Understand API Gateway vs ALB as an API front door | 02/23/2026 | 02/23/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 (Tue) | - **Practice:** <br>&emsp; + Create a REST API with GET /hello resource <br>&emsp; + Use Mock integration to return a static response <br>&emsp; + Deploy to a `dev` stage and test with curl | 02/24/2026 | 02/24/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 (Wed) | - Learn API Gateway request/response mapping: Method Request, Integration Request, Method Response <br> - Study Mapping Templates (VTL) for request transformation <br> - Configure CORS headers | 02/25/2026 | 02/25/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 (Thu) | - Learn API Gateway security: API Keys + Usage Plans, Resource Policies, IAM authorization <br> - **Practice:** <br>&emsp; + Create an API Key and Usage Plan with rate limiting <br>&emsp; + Attach key to a stage and test throttled responses | 02/26/2026 | 02/26/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 (Fri) | - Learn API Gateway stages and deployment strategies <br> - Study stage variables and canary deployments <br> - **Practice:** Configure two stages (dev/prod) with different throttle settings and stage variables | 02/27/2026 | 02/27/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Week 8 Achievements:

* Understood the differences between REST API, HTTP API, and WebSocket API in API Gateway.
* Created and deployed a REST API with a mock integration to a named stage.
* Configured CORS and request/response mapping templates using VTL.
* Implemented API Key authentication with Usage Plans and verified throttling behavior.
* Set up dev and prod deployment stages with distinct configurations using stage variables.
* ...
