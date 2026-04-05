---
title : "Kiểm tra Backend Microservices"
date : 2024-01-01 
weight : 4
chapter : false
pre : " <b> 4.4. </b> "
---

#### Xác minh các dịch vụ ECS chạy trên Fargate

Các microservice của hệ thống hoạt động bên trong vùng mạng riêng tư (private subnet) và giao tiếp với nhau thông qua Application Load Balancer (ALB) nội bộ — không công khai trực tiếp ra Internet.

---

### 1. Amazon ECS (Elastic Container Service)

Amazon ECS là dịch vụ quản lý và điều phối các container Docker. Kết hợp với AWS Fargate (mô hình serverless), bạn không cần quan tâm đến máy chủ vật lý bên dưới — AWS tự động cấp phát CPU và RAM vừa đủ để chạy từng container.

**Kiểm tra trạng thái ECS Clusters và Services:**

- Nhập **ECS** vào thanh tìm kiếm và chọn **Elastic Container Service**.

![Tìm kiếm dịch vụ ECS](/4-workshop/4.4-verify-backend/image.png)

- Chọn Cluster tương ứng và xem danh sách các service (`auth-service`, `event-service`, `ticket-service`, `venue-service`, `notification-service`).

![Danh sách các ECS Service](/4-workshop/4.4-verify-backend/image-1.png)

- Đảm bảo tất cả service đều ở trạng thái **Active**.

![Trạng thái Active của Service](/4-workshop/4.4-verify-backend/image-2.png)

- Xác nhận số lượng **Running Tasks** khớp với cấu hình mong muốn.

![Kiểm tra số lượng Running Tasks](/4-workshop/4.4-verify-backend/image-3.png)

---

### 2. Application Load Balancer (ALB) & Target Groups

Application Load Balancer là bộ phân phối tải thông minh — nó nhận yêu cầu từ API Gateway và chuyển tiếp đến đúng container backend đang rảnh. Target Groups xác định tập hợp container nào nhận lưu lượng từ mỗi route.

**Kiểm tra Target Groups đang ở trạng thái Healthy:**

- Nhập **EC2** vào thanh tìm kiếm và truy cập **EC2 Console**.

![Tìm kiếm EC2 Console](/4-workshop/4.4-verify-backend/image-4.png)

- Ở thanh menu bên trái, cuộn xuống phần **Load Balancing** và chọn **Load Balancers**.

![Chọn Load Balancers](/4-workshop/4.4-verify-backend/image-5.png)

- Chọn ALB nội bộ của hệ thống (ví dụ: `fpt-event-alb`).

![Chọn ALB nội bộ](/4-workshop/4.4-verify-backend/image-6.png)

- Chọn tab **Listeners and rules** để xem các cấu hình định tuyến.

![Kiểm tra Listeners and Rules](/4-workshop/4.4-verify-backend/image-7.png)

- Truy cập **Target Groups** (thanh menu bên trái, bên dưới Load Balancers) và đảm bảo tất cả container đều vượt qua Health Check với trạng thái **Healthy**.

![Trạng thái Healthy của Target Groups](/4-workshop/4.4-verify-backend/image-8.png)

![Chi tiết Target Group Health Check](/4-workshop/4.4-verify-backend/image-9.png)