---
title: "Week 5 Worklog"
date: 2026-02-02
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Understand the types of Elastic Load Balancers and select the right one per use case.
* Configure Application Load Balancer (ALB) with advanced routing rules and health checks.
* Set up Network Load Balancer (NLB) for high-performance TCP/UDP workloads.
* Integrate Load Balancer with Auto Scaling Group for elastic traffic distribution.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 (Mon) | - Study ELB types: ALB (Layer 7 / HTTP), NLB (Layer 4 / TCP), GWLB (Layer 3 / appliances) <br> - Understand Listeners, Rules, Target Groups, and health check configurations | 02/02/2026 | 02/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 (Tue) | - **Practice:** <br>&emsp; + Create an ALB with an HTTP:80 listener <br>&emsp; + Register EC2 instances into a Target Group <br>&emsp; + Configure health check path (/) and thresholds <br>&emsp; + Verify traffic distribution across instances | 02/03/2026 | 02/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 (Wed) | - Configure ALB advanced listener rules: <br>&emsp; + Path-based routing: /api/* → backend TG, /* → frontend TG <br>&emsp; + Host-based routing: app.example.com vs api.example.com <br>&emsp; + Redirect HTTP → HTTPS | 02/04/2026 | 02/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 (Thu) | - Learn NLB differences: static IP, TCP pass-through, ultra-low latency, TLS termination <br> - **Practice:** <br>&emsp; + Create NLB with TCP:80 listener and Target Group <br>&emsp; + Compare response time between ALB and NLB | 02/05/2026 | 02/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 (Fri) | - Learn ALB + ASG integration patterns <br> - **Practice:** <br>&emsp; + Attach ALB Target Group to existing Auto Scaling Group <br>&emsp; + Trigger a scale-out event and verify new instances receive traffic <br>&emsp; + Review access logs and CloudWatch metrics | 02/06/2026 | 02/06/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Week 5 Achievements:

* Understood the differences between ALB, NLB, and GWLB and their appropriate use cases.
* Created an ALB with health-checked Target Groups and verified even traffic distribution.
* Configured path-based and host-based routing rules on ALB for a multi-service architecture.
* Deployed an NLB for TCP workloads and observed lower latency compared to ALB.
* Integrated ALB with an Auto Scaling Group; verified new instances automatically received traffic on scale-out.
* Analyzed ALB access logs and CloudWatch metrics (RequestCount, TargetResponseTime).
* ...
