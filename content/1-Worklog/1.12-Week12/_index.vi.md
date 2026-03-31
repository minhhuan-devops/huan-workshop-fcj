---
title: "Worklog Tuần 12"
date: 2026-03-23
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu tuần 12:

* Hiểu Retrieval-Augmented Generation (RAG) và lý do nó cải thiện độ chính xác của LLM.
* Tạo và cấu hình Bedrock Knowledge Base với S3 làm data source.
* Thiết lập vector embeddings, OpenSearch Serverless và kiểm tra semantic search queries.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Hiểu kiến trúc RAG: tại sao LLM bị ảo giác và cách grounding bằng retrieval giúp ích <br> - Tìm hiểu các thành phần RAG: data ingestion, chunking, vector embedding, vector store, retrieval, augmentation | 23/03/2026 | 23/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Tìm hiểu Bedrock Knowledge Bases: các data source được hỗ trợ (S3, Confluence, SharePoint) <br> - Nghiên cứu các tùy chọn vector store: OpenSearch Serverless, Pinecone, Aurora pgvector <br> - Học các chiến lược chunking: fixed size, hierarchical, semantic | 24/03/2026 | 24/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - **Thực hành:** <br>&emsp; + Upload tài liệu PDF/text lên S3 làm data source Knowledge Base <br>&emsp; + Tạo Bedrock Knowledge Base với Titan Embeddings v2 <br>&emsp; + Tạo OpenSearch Serverless collection làm vector store | 25/03/2026 | 25/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - **Thực hành:** <br>&emsp; + Kích hoạt Knowledge Base sync (data ingestion & embedding) <br>&emsp; + Test semantic retrieval trong Bedrock console (Retrieve API) <br>&emsp; + Dùng RetrieveAndGenerate API để nhận câu trả lời có căn cứ từ Claude 3 | 26/03/2026 | 26/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Nghiên cứu session context KB & nguồn trích dẫn trong response <br> - Tìm hiểu cách cập nhật KB: thêm tài liệu mới, re-sync <br> - **Thực hành:** Thêm tài liệu mới vào S3, re-sync và xác nhận cải thiện retrieval | 27/03/2026 | 27/03/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 12:

* Hiểu mô hình RAG và cách grounding response LLM bằng tài liệu được truy xuất giảm ảo giác.
* Tạo Bedrock Knowledge Base kết nối S3 và OpenSearch Serverless vector store.
* Kích hoạt data ingestion, theo dõi chunking và embedding, xác nhận tạo index thành công.
* Truy vấn Knowledge Base với Retrieve API và nhận các document chunk liên quan về ngữ nghĩa.
* Dùng RetrieveAndGenerate API để nhận câu trả lời Claude 3 có căn cứ từ Knowledge Base kèm trích dẫn.
* Cập nhật Knowledge Base với tài liệu mới và re-sync để xác nhận kết quả retrieval mới nhất.
* ...
