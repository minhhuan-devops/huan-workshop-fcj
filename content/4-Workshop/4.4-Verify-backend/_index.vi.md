---
title : "Kiểm tra Backend Microservices"
date : 2024-01-01 
weight : 4
chapter : false
pre : " <b> 4.4. </b> "
---

#### Xác minh các dịch vụ ECS chạy trên Fargate

Các microservices của hệ thống được lập trình ẩn ở vùng mạng riêng tư tư (private subnet) và giao tiếp thông qua Application Load Balancer (ALB) nội bộ, thay vì public trực tiếp ra Internet.

1. **Kiểm tra trạng thái ECS Clusters và Services:**
   - Truy cập **Amazon ECS Console** trên thanh tìm kiếm.
   
   ![Giao diện tìm kiếm ECS](/4-workshop/4.4-verify-backend/image.png)
   
   - Chọn Cluster tương ứng và kiểm tra danh sách các dịch vụ (`auth-service`, `event-service`, `ticket-service`, `venue-service`, `notification-service`).
   
   ![Danh sách các ECS Service](/4-workshop/4.4-verify-backend/image-1.png)
   
   - Đảm bảo rằng tất cả các service đều đang ở trạng thái triển khai thành công (**Active** / **Running**).
   
   ![Trạng thái Service](/4-workshop/4.4-verify-backend/image-2.png)
   
   - Đảm bảo số lượng **Running Tasks** khớp với yêu cầu hệ thống định sẵn.
   
   ![Kiểm tra số lượng task](/4-workshop/4.4-verify-backend/image-3.png)

2. **Kiểm tra Target Groups ở Application Load Balancer:**
   - Để kiểm tra khả năng định tuyến đến các container, vào giao diện **EC2 Console**.
   
   ![Giao diện tìm kiếm EC2](/4-workshop/4.4-verify-backend/image-4.png)
   
   - Ở thanh menu bên trái, cuộn xuống phần **Load Balancing** và chọn **Load Balancers**.
   
   ![Chọn Load Balancers](/4-workshop/4.4-verify-backend/image-5.png)
   
   - Chọn ALB nội bộ của hệ thống (ví dụ: `fpt-event-alb`).
   
   ![Chọn ALB nội bộ](/4-workshop/4.4-verify-backend/image-6.png)
   
   - Qua tab **Listeners and rules** để kiểm tra các cấu hình định tuyến.
   
   ![Kiểm tra Listeners and Rules](/4-workshop/4.4-verify-backend/image-7.png)
   
   - Truy cập phần **Target Groups** (ở thanh menu bên trái, phía dưới Load Balancers), xem từng Target Group và đảm bảo tất cả các container đều vượt qua Health Check (trạng thái **Healthy**).
   
   ![Trạng thái Healthy Target Groups](/4-workshop/4.4-verify-backend/image-8.png)
    ![alt text](/4-workshop/4.4-verify-backend/image-9.png)