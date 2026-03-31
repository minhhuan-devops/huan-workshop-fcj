---
title: "Week 2 Worklog"
date: 2026-01-12
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

* Enable private subnet instances to securely access the internet via NAT Gateway.
* Connect AWS services privately without public internet using VPC Endpoints.
* Link multiple VPCs together using VPC Peering.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 (Mon) | - Review Week 1 VPC setup <br> - Learn NAT Gateway vs NAT Instance: differences in cost, availability, and management | 01/12/2026 | 01/12/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 (Tue) | - **Practice:** <br>&emsp; + Create a NAT Gateway in the public subnet <br>&emsp; + Update private route table to route 0.0.0.0/0 → NAT Gateway <br>&emsp; + Verify internet access from private EC2 instance | 01/13/2026 | 01/13/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 (Wed) | - Learn VPC Endpoints: Interface Endpoint vs Gateway Endpoint <br> - Understand use cases: S3, DynamoDB (Gateway), SSM, ECR (Interface) <br> - Study endpoint policies | 01/14/2026 | 01/14/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 (Thu) | - **Practice:** <br>&emsp; + Create a Gateway Endpoint for S3 <br>&emsp; + Access S3 from private subnet without internet routing <br>&emsp; + Create Interface Endpoint for SSM & test session manager | 01/15/2026 | 01/15/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 (Fri) | - Learn VPC Peering: concepts, CIDR requirements, route table updates <br> - Understand transitive peering limitation & AWS Transit Gateway overview <br> - **Practice:** Peer two VPCs & test cross-VPC EC2 connectivity | 01/16/2026 | 01/16/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Week 2 Achievements:

* Deployed a NAT Gateway and verified private subnet instances can reach the internet.
* Understood cost and resilience differences between NAT Gateway and NAT Instance.
* Created a VPC Gateway Endpoint for S3; confirmed traffic stays within the AWS network.
* Set up an Interface Endpoint for SSM and connected to a private EC2 without a bastion host.
* Successfully established VPC Peering between two VPCs and updated route tables accordingly.
* Understood transitive peering limitations and when to use AWS Transit Gateway.
* ...
