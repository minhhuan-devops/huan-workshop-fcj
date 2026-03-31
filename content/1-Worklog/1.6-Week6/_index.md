---
title: "Week 6 Worklog"
date: 2026-02-09
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

* Understand containerization concepts with Docker and how containers differ from VMs.
* Learn to build, tag, and push Docker images to Amazon Elastic Container Registry (ECR).
* Set up ECR repositories and integrate them with IAM authentication.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 (Mon) | - Introduction to containerization: Docker vs Virtual Machines <br> - Learn Docker core concepts: images, containers, layers, Dockerfile, volumes, networks | 02/09/2026 | 02/09/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 (Tue) | - **Practice:** <br>&emsp; + Write a Dockerfile for a Node.js/Python app <br>&emsp; + Build image: `docker build` <br>&emsp; + Run container locally: `docker run` <br>&emsp; + Inspect layers with `docker inspect` | 02/10/2026 | 02/10/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 (Wed) | - Learn Amazon ECR: private vs public repositories, image scanning, lifecycle policies <br> - Understand ECR authentication with `aws ecr get-login-password` | 02/11/2026 | 02/11/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 (Thu) | - **Practice:** <br>&emsp; + Create a private ECR repository <br>&emsp; + Authenticate Docker to ECR <br>&emsp; + Tag & push image to ECR <br>&emsp; + Enable image vulnerability scanning | 02/12/2026 | 02/12/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 (Fri) | - Learn ECR image lifecycle policies (expire untagged images) <br> - Study Docker multi-stage builds for smaller images <br> - **Practice:** Implement multi-stage Dockerfile and compare image sizes | 02/13/2026 | 02/13/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Week 6 Achievements:

* Understood how Docker containers differ from VMs in terms of isolation and resource usage.
* Wrote a Dockerfile and built a working container image for a web application.
* Created a private ECR repository and successfully pushed a tagged image.
* Enabled ECR image scanning and reviewed vulnerability findings.
* Applied ECR lifecycle policies to automatically remove old untagged images.
* Implemented multi-stage Docker builds to produce lean production images.
* ...
