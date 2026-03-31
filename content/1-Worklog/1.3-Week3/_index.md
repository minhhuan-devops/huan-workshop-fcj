---
title: "Week 3 Worklog"
date: 2026-01-19
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* Understand EC2 instance types, purchase options, and lifecycle management.
* Create and manage Amazon Machine Images (AMI) as reusable server templates.
* Work with Amazon EBS: volume types, snapshots, encryption, and resizing.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 (Mon) | - Study EC2 instance families: General Purpose (t/m), Compute (c), Memory (r/x), Storage (i/d) <br> - Compare On-Demand vs Reserved vs Spot vs Savings Plans pricing | 01/19/2026 | 01/19/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 (Tue) | - Learn AMI concepts: public, private, and AWS Marketplace AMIs <br> - Understand AMI lifecycle: create, share, copy across regions <br> - **Practice:** Launch EC2 with a custom user data bootstrap script | 01/20/2026 | 01/20/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 (Wed) | - **Practice:** <br>&emsp; + Configure an EC2 instance (install Nginx, set up web page) <br>&emsp; + Create a custom AMI from the running instance <br>&emsp; + Launch a new instance from the custom AMI and verify | 01/21/2026 | 01/21/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 (Thu) | - Learn EBS volume types: gp3, io2 Block Express, st1, sc1 <br> - Understand EBS Multi-Attach, encryption (KMS), and Lifecycle Manager <br> - Study EBS vs Instance Store trade-offs | 01/22/2026 | 01/22/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 (Fri) | - **Practice:** <br>&emsp; + Attach & format a new EBS gp3 volume to EC2 <br>&emsp; + Create an EBS snapshot and restore to a new volume <br>&emsp; + Resize a volume online (extend without downtime) | 01/23/2026 | 01/23/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Week 3 Achievements:

* Understood EC2 instance families and selected appropriate types for different workloads.
* Compared On-Demand, Reserved, Spot, and Savings Plans pricing to identify cost-saving strategies.
* Created a custom AMI from a configured EC2 instance and launched identical servers from it.
* Attached, formatted, and mounted EBS volumes; performed live volume resize without downtime.
* Created EBS snapshots and restored data successfully to a new volume.
* Understood the difference between EBS (persistent) and Instance Store (ephemeral) storage.
* ...
