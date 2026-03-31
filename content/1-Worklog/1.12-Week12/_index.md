---
title: "Week 12 Worklog"
date: 2026-03-23
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Week 12 Objectives:

* Understand Retrieval-Augmented Generation (RAG) and why it improves LLM accuracy.
* Create and configure a Bedrock Knowledge Base backed by an S3 data source.
* Set up vector embeddings, OpenSearch Serverless, and test semantic search queries.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 (Mon) | - Understand RAG architecture: why LLMs hallucinate and how retrieval grounding helps <br> - Learn RAG components: data ingestion, chunking, vector embedding, vector store, retrieval, augmentation | 03/23/2026 | 03/23/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 (Tue) | - Learn Amazon Bedrock Knowledge Bases: supported data sources (S3, Confluence, SharePoint) <br> - Study vector store options: OpenSearch Serverless, Pinecone, Aurora pgvector <br> - Learn chunking strategies: fixed size, hierarchical, semantic | 03/24/2026 | 03/24/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 (Wed) | - **Practice:** <br>&emsp; + Upload PDF/text documents to S3 as the Knowledge Base data source <br>&emsp; + Create a Bedrock Knowledge Base with Titan Embeddings v2 <br>&emsp; + Create an OpenSearch Serverless collection as the vector store | 03/25/2026 | 03/25/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 (Thu) | - **Practice:** <br>&emsp; + Trigger Knowledge Base sync (data ingestion & embedding) <br>&emsp; + Test semantic retrieval in the Bedrock console (Retrieve API) <br>&emsp; + Use RetrieveAndGenerate API to get grounded answers from Claude 3 | 03/26/2026 | 03/26/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 (Fri) | - Study Knowledge Base session context & citation sources in responses <br> - Learn how to update the KB: add new documents, re-sync <br> - **Practice:** Add new documents to S3, re-sync, and verify retrieval improvements | 03/27/2026 | 03/27/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Week 12 Achievements:

* Understood the RAG pattern and how grounding LLM responses with retrieved documents reduces hallucination.
* Created a Bedrock Knowledge Base connected to an S3 data source and OpenSearch Serverless vector store.
* Triggered data ingestion, monitored chunking and embedding, and verified index creation.
* Queried the Knowledge Base with the Retrieve API and received semantically relevant document chunks.
* Used RetrieveAndGenerate API to get Claude 3 responses grounded in Knowledge Base content with citations.
* Updated Knowledge Base with new documents and re-synced to verify fresh retrieval results.
* ...
