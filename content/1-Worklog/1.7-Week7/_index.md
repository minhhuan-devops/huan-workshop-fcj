---
title: "Week 7 Worklog"
date: 2026-02-16
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

* Understand Amazon ECS architecture: clusters, services, tasks, and task definitions.
* Configure ECS Task Definitions with container definitions, resource limits, and IAM roles.
* Deploy containerized workloads on AWS Fargate (serverless data plane).

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 (Mon) | - Learn ECS architecture: Clusters, Services, Tasks, Task Definitions <br> - Compare ECS launch types: EC2 vs Fargate vs ECS Anywhere <br> - Understand ECS vs EKS trade-offs | 02/16/2026 | 02/16/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 (Tue) | - Learn ECS Task Definition structure: container definitions, CPU/memory, port mappings, environment variables, secrets (SSM/Secrets Manager) <br> - Understand Task Role vs Task Execution Role | 02/17/2026 | 02/17/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 (Wed) | - **Practice:** <br>&emsp; + Create an ECS Cluster (Fargate) <br>&emsp; + Create a Task Definition using ECR image from Week 6 <br>&emsp; + Run a standalone task and verify logs in CloudWatch | 02/18/2026 | 02/18/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 (Thu) | - Learn ECS Services: desired count, deployment strategies (Rolling, Blue/Green), circuit breaker <br> - **Practice:** <br>&emsp; + Create an ECS Service (Fargate) behind an ALB <br>&emsp; + Configure service auto-scaling based on CPU | 02/19/2026 | 02/19/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 (Fri) | - Learn ECS networking: awsvpc mode, Security Groups per task <br> - **Practice:** <br>&emsp; + Update task to use awsvpc networking <br>&emsp; + Deploy new task definition revision via rolling update <br>&emsp; + Validate zero-downtime deployment | 02/20/2026 | 02/20/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Week 7 Achievements:

* Understood ECS components: clusters, services, task definitions, and tasks.
* Created an ECS Task Definition referencing an ECR image with proper IAM execution role.
* Deployed a containerized application on Fargate and verified logs in CloudWatch Logs.
* Created an ECS Service with ALB integration and confirmed traffic routing to containers.
* Configured ECS Service Auto Scaling based on CPU utilization.
* Performed a rolling deployment update with zero downtime using ECS circuit breaker.
* ...
