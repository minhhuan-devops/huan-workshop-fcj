---
title: "Worklog Tuần 7"
date: 2026-02-16
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* Hiểu kiến trúc Amazon ECS: clusters, services, tasks và task definitions.
* Cấu hình ECS Task Definitions với container definitions, giới hạn tài nguyên và IAM roles.
* Triển khai workload container hóa trên AWS Fargate (serverless data plane).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Tìm hiểu kiến trúc ECS: Clusters, Services, Tasks, Task Definitions <br> - So sánh ECS launch types: EC2 vs Fargate vs ECS Anywhere <br> - Hiểu sự đánh đổi giữa ECS và EKS | 16/02/2026 | 16/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Tìm hiểu cấu trúc ECS Task Definition: container definitions, CPU/memory, port mappings, biến môi trường, secrets (SSM/Secrets Manager) <br> - Hiểu sự khác biệt Task Role và Task Execution Role | 17/02/2026 | 17/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - **Thực hành:** <br>&emsp; + Tạo ECS Cluster (Fargate) <br>&emsp; + Tạo Task Definition dùng ECR image từ tuần 6 <br>&emsp; + Chạy standalone task và xem logs trong CloudWatch | 18/02/2026 | 18/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Tìm hiểu ECS Services: desired count, chiến lược deployment (Rolling, Blue/Green), circuit breaker <br> - **Thực hành:** <br>&emsp; + Tạo ECS Service (Fargate) phía sau ALB <br>&emsp; + Cấu hình service auto-scaling theo CPU | 19/02/2026 | 19/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Tìm hiểu ECS networking: awsvpc mode, Security Groups per task <br> - **Thực hành:** <br>&emsp; + Cập nhật task dùng awsvpc networking <br>&emsp; + Deploy task definition revision mới qua rolling update <br>&emsp; + Xác nhận zero-downtime deployment | 20/02/2026 | 20/02/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 7:

* Hiểu các thành phần ECS: clusters, services, task definitions và tasks.
* Tạo ECS Task Definition tham chiếu ECR image với IAM execution role phù hợp.
* Triển khai ứng dụng container hóa trên Fargate và xem logs trong CloudWatch Logs.
* Tạo ECS Service tích hợp ALB và xác nhận routing traffic đến containers.
* Cấu hình ECS Service Auto Scaling dựa trên CPU utilization.
* Thực hiện rolling deployment update không gián đoạn với ECS circuit breaker.
* ...
