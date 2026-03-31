---
title: "Week 4 Worklog"
date: 2026-01-26
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

* Understand advanced EC2 features: placement groups, metadata, and secure access patterns.
* Create Launch Templates and deploy Auto Scaling Groups (ASG) with dynamic scaling policies.
* Design a self-healing, fault-tolerant architecture using ASG lifecycle hooks.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 (Mon) | - Learn EC2 placement groups: Cluster (low latency), Spread (fault isolation), Partition (distributed workloads) <br> - Study Enhanced Networking (ENA) and its performance benefits | 01/26/2026 | 01/26/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 (Tue) | - Learn EC2 Instance Metadata Service v2 (IMDSv2) and User Data <br> - **Practice:** <br>&emsp; + Query instance metadata via IMDSv2 (token-based) <br>&emsp; + Use User Data to bootstrap Nginx on launch | 01/27/2026 | 01/27/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 (Wed) | - Learn Launch Templates vs Launch Configurations (why LT is preferred) <br> - **Practice:** Create a Launch Template with: AMI, instance type, SG, key pair, user data, and tags | 01/28/2026 | 01/28/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 (Thu) | - **Practice:** <br>&emsp; + Create an Auto Scaling Group using the Launch Template <br>&emsp; + Configure min=1, max=4, desired=2 across multi-AZ <br>&emsp; + Set up Target Tracking Scaling Policy (CPU utilization 50%) | 01/29/2026 | 01/29/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 (Fri) | - Learn ASG lifecycle hooks (launching & terminating events) <br> - **Practice:** <br>&emsp; + Simulate instance failure and observe ASG auto-replacement <br>&emsp; + Trigger CPU load and watch scale-out event <br>&emsp; + Review scaling activity history | 01/30/2026 | 01/30/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Week 4 Achievements:

* Understood EC2 placement group strategies and their impact on latency and fault isolation.
* Queried instance metadata securely using IMDSv2 token-based authentication.
* Created a versioned Launch Template covering all instance configuration parameters.
* Deployed an ASG across multiple AZs with target tracking scaling on CPU utilization.
* Verified ASG automatically replaces a terminated instance to maintain desired capacity.
* Observed and analyzed scale-out events through CloudWatch metrics and ASG activity logs.
* ...
