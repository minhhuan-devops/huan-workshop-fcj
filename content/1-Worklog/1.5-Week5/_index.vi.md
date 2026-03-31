---
title: "Worklog Tuần 5"
date: 2026-02-02
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Hiểu các loại Elastic Load Balancer và chọn đúng loại cho từng use case.
* Cấu hình Application Load Balancer (ALB) với các routing rule nâng cao và health checks.
* Thiết lập Network Load Balancer (NLB) cho workload TCP/UDP hiệu suất cao.
* Tích hợp Load Balancer với Auto Scaling Group để phân phối traffic linh hoạt.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Học các loại ELB: ALB (Layer 7 / HTTP), NLB (Layer 4 / TCP), GWLB (Layer 3 / thiết bị ảo) <br> - Hiểu Listeners, Rules, Target Groups và cấu hình health check | 02/02/2026 | 02/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - **Thực hành:** <br>&emsp; + Tạo ALB với listener HTTP:80 <br>&emsp; + Đăng ký EC2 instances vào Target Group <br>&emsp; + Cấu hình health check path (/) và ngưỡng <br>&emsp; + Kiểm tra phân phối traffic đều giữa các instance | 03/02/2026 | 03/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Cấu hình ALB listener rules nâng cao: <br>&emsp; + Path-based routing: /api/* → backend TG, /* → frontend TG <br>&emsp; + Host-based routing: app.example.com vs api.example.com <br>&emsp; + Chuyển hướng HTTP → HTTPS | 04/02/2026 | 04/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Tìm hiểu điểm khác biệt NLB: static IP, TCP pass-through, độ trễ cực thấp, TLS termination <br> - **Thực hành:** <br>&emsp; + Tạo NLB với listener TCP:80 và Target Group <br>&emsp; + So sánh response time giữa ALB và NLB | 05/02/2026 | 05/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Tìm hiểu mô hình tích hợp ALB + ASG <br> - **Thực hành:** <br>&emsp; + Gắn ALB Target Group vào Auto Scaling Group hiện có <br>&emsp; + Kích hoạt scale-out và xác nhận instance mới nhận traffic <br>&emsp; + Xem access logs và CloudWatch metrics | 06/02/2026 | 06/02/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 5:

* Hiểu sự khác biệt giữa ALB, NLB và GWLB và use case phù hợp của từng loại.
* Tạo ALB với Target Group có health check và xác nhận phân phối traffic đều.
* Cấu hình path-based và host-based routing rules trên ALB cho kiến trúc đa dịch vụ.
* Triển khai NLB cho TCP workloads và quan sát độ trễ thấp hơn ALB.
* Tích hợp ALB với Auto Scaling Group; xác nhận instance mới tự động nhận traffic khi scale-out.
* Phân tích ALB access logs và CloudWatch metrics (RequestCount, TargetResponseTime).
* ...
