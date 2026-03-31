---
title: "Worklog Tuần 13"
date: 2026-03-30
weight: 13
chapter: false
pre: " <b> 1.13. </b> "
---

### Mục tiêu tuần 13:

* Xây dựng một Amazon Bedrock Agent đầy đủ chức năng với Action Groups và tích hợp Knowledge Base.
* Kết nối Agent với các công cụ thực tế qua Lambda Action Groups.
* Thực hiện tổng kết cuối khóa 13 tuần và chuẩn bị demo dự án.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Giới thiệu Bedrock Agents: Agent khác với LLM call thông thường như thế nào <br> - Tìm hiểu các thành phần agent: Instructions, Action Groups, Knowledge Base, Memory, Guardrails <br> - Hiểu vòng lặp ReAct (Reasoning + Acting) mà agent sử dụng | 30/03/2026 | 30/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - **Thực hành:** <br>&emsp; + Tạo Bedrock Agent với system prompt (persona & phạm vi nhiệm vụ) <br>&emsp; + Gắn Knowledge Base từ tuần 12 vào Agent <br>&emsp; + Test Agent trong console với câu hỏi đa lượt dựa trên nội dung KB | 31/03/2026 | 31/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Tìm hiểu Action Groups: định nghĩa OpenAPI schema, gọi Lambda function <br> - **Thực hành:** <br>&emsp; + Viết Lambda function (ví dụ: tra cứu thời tiết / truy vấn DB) <br>&emsp; + Định nghĩa Action Group với OpenAPI schema <br>&emsp; + Gắn Action Group vào Agent và test gọi tool | 01/04/2026 | 01/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Tìm hiểu Agent aliases và versioning để promote (dev → prod) <br> - Nghiên cứu Agent memory (lưu ngữ cảnh session) và prompt override templates <br> - **Thực hành:** <br>&emsp; + Tạo Agent alias (prod) và invoke qua Bedrock SDK <br>&emsp; + Trace các bước lý luận agent với `enableTrace: true` | 02/04/2026 | 02/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Tổng kết cuối khóa: ôn lại 13 tuần (VPC → EC2 → LB → ECS → API GW → CloudFront → Bedrock) <br> - Chuẩn bị demo dự án trình bày Bedrock Agent end-to-end <br> - Ghi lại bài học kinh nghiệm, thách thức đã gặp và các bước tiếp theo | 03/04/2026 | 03/04/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 13:

* Xây dựng Bedrock Agent với persona instructions, tích hợp Knowledge Base và Action Groups.
* Định nghĩa OpenAPI schema cho Action Group và kết nối với Lambda function tool.
* Xác nhận Agent sử dụng đúng RAG Knowledge Base để trả lời câu hỏi chuyên môn kèm trích dẫn.
* Trace vòng lặp lý luận ReAct (Thought → Action → Observation → Response) trong quá trình thực thi agent.
* Tạo Agent alias có version và gọi theo chương trình qua boto3.
* Hoàn thành hành trình học AWS 13 tuần có cấu trúc từ nền tảng mạng đến Generative AI.
* Trình bày demo dự án thể hiện hạ tầng và khả năng AI được xây dựng trong suốt chương trình.
* ...
