---
title : "Kiểm tra Backend Microservices"
date : 2024-01-01 
weight : 4
chapter : false
pre : " <b> 4.4. </b> "
---

#### Xác minh các dịch vụ ECS chạy trên Fargate

Các microservices của chúng ta không được public trực tiếp ra Internet mà nằm sau Application Load Balancer (ALB) nội bộ.

1. Truy cập **Amazon ECS Console**.
2. Kiểm tra trạng thái của các Clusters và Services (`auth-service`, `event-service`, `ticket-service`, `notification-service`).
3. Đảm bảo số lượng **Running Tasks** khớp với cấu hình mà Terraform đã triển khai.
4. Kiểm tra **Target Groups** trong giao diện EC2 để đảm bảo tất cả các container đều vượt qua Health Check và ở trạng thái **Healthy**.
5. Thử gọi API thông qua ALB nội bộ DNS (sử dụng curl từ Bastion host).
