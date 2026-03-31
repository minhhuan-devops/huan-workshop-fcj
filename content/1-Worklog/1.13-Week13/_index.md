---
title: "Week 13 Worklog"
date: 2026-03-30
weight: 13
chapter: false
pre: " <b> 1.13. </b> "
---

### Week 13 Objectives:

* Build a fully functional Amazon Bedrock Agent with Action Groups and Knowledge Base integration.
* Connect the Agent to real-world tools via Lambda Action Groups.
* Conduct a final review of the 13-week learning journey and produce a project demo.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 (Mon) | - Introduction to Bedrock Agents: how agents differ from plain LLM calls <br> - Learn agent components: Instructions, Action Groups, Knowledge Base, Memory, Guardrails <br> - Understand the ReAct (Reasoning + Acting) loop used by agents | 03/30/2026 | 03/30/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 (Tue) | - **Practice:** <br>&emsp; + Create a Bedrock Agent with a system prompt (persona & task scope) <br>&emsp; + Attach the Knowledge Base from Week 12 to the Agent <br>&emsp; + Test Agent in the console with multi-turn questions against KB content | 03/31/2026 | 03/31/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 (Wed) | - Learn Action Groups: OpenAPI schema definition, Lambda function invocation <br> - **Practice:** <br>&emsp; + Write a Lambda function (e.g., weather lookup / DB query) <br>&emsp; + Define an Action Group with OpenAPI schema <br>&emsp; + Attach Action Group to Agent and test tool invocation | 04/01/2026 | 04/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 (Thu) | - Learn Agent aliases and versioning for promotion (dev → prod) <br> - Study Agent memory (session context retention) and prompt override templates <br> - **Practice:** <br>&emsp; + Create an Agent alias (prod) and invoke via Bedrock SDK <br>&emsp; + Trace the agent reasoning steps with `enableTrace: true` | 04/02/2026 | 04/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 (Fri) | - Final Review: recap all 13 weeks (VPC → EC2 → LB → ECS → API GW → CloudFront → Bedrock) <br> - Prepare project demo showcasing the Bedrock Agent end-to-end <br> - Document lessons learned, challenges faced, and next steps | 04/03/2026 | 04/03/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Week 13 Achievements:

* Built a Bedrock Agent with persona instructions, Knowledge Base integration, and Action Groups.
* Defined an OpenAPI schema for an Action Group and wired it to a Lambda function tool.
* Verified the Agent correctly used the RAG Knowledge Base to answer domain-specific questions with citations.
* Traced the ReAct reasoning loop (Thought → Action → Observation → Response) in agent execution.
* Created a versioned Agent alias and invoked it programmatically via boto3.
* Completed a 13-week structured AWS learning journey from foundational networking to Generative AI.
* Delivered a project demo showcasing infrastructure and AI capabilities built throughout the program.
* ...
