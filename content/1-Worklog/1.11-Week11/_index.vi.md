---
title: "Worklog Tuần 11"
date: 2026-03-16
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

* Hiểu các kiến thức cơ bản về Generative AI và bức tranh các mô hình ngôn ngữ lớn (LLM).
* Khám phá Amazon Bedrock: Foundation Models, truy cập model và Bedrock console.
* Học kỹ thuật prompt engineering và gọi model qua Bedrock API.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Giới thiệu Generative AI: LLM là gì, transformers, tokens và embeddings <br> - Tổng quan hệ sinh thái Gen AI: OpenAI, Anthropic, Meta, Mistral, Amazon Titan <br> - Tìm hiểu Bedrock khác SageMaker cho Gen AI workloads như thế nào | 16/03/2026 | 16/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Khám phá Bedrock console: danh mục model, yêu cầu truy cập model <br> - Tìm hiểu các loại Foundation Model: sinh văn bản, embeddings, sinh ảnh <br> - **Thực hành:** Bật quyền truy cập model Claude 3, Titan và Llama 3 trong Bedrock | 17/03/2026 | 17/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Tìm hiểu prompt engineering: zero-shot, few-shot, chain-of-thought prompting <br> - Học system prompts vs user prompts và các tham số temperature/top-p <br> - **Thực hành:** Thử nghiệm prompts trong Bedrock Playground (chế độ text & chat) | 18/03/2026 | 18/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Tìm hiểu Bedrock API: `InvokeModel`, `InvokeModelWithResponseStream` <br> - **Thực hành:** <br>&emsp; + Gọi Bedrock API qua AWS SDK (Python boto3) <br>&emsp; + Invoke Claude 3 với structured prompt <br>&emsp; + Xử lý streaming responses | 19/03/2026 | 19/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Tìm hiểu Bedrock Guardrails: lọc nội dung, ẩn PII, từ chối chủ đề <br> - Nghiên cứu Bedrock Model Evaluation và thực hành AI có trách nhiệm <br> - **Thực hành:** Cấu hình Guardrail cơ bản và test kết quả bị chặn | 20/03/2026 | 20/03/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 11:

* Hiểu các khái niệm GenAI cốt lõi: transformers, tokenization, embeddings và các tham số suy luận.
* Bật quyền truy cập nhiều Foundation Models (Claude 3, Titan, Llama 3) trong Amazon Bedrock.
* Áp dụng kỹ thuật zero-shot và few-shot prompt engineering trong Bedrock Playground.
* Gọi Claude 3 qua Python boto3 SDK và xử lý streaming response theo từng chunk.
* Cấu hình Bedrock Guardrail để lọc nội dung và test với các chủ đề bị hạn chế.
* Hiểu các cân nhắc AI có trách nhiệm khi triển khai Foundation Models trong production.
* ...
