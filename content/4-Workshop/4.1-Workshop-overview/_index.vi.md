---
title : "Giới thiệu"
date : 2024-01-01 
weight : 1
chapter : false
pre : " <b> 4.1. </b> "
---

#### Tổng quan Kiến trúc

**Hệ thống Quản lý Sự kiện FPT** tận dụng các dịch vụ Cloud hiện đại, triển khai kiến trúc microservices (hướng sự kiện) trên AWS. Hệ thống được thiết kế để chịu tải cao trong các đợt mở bán vé khối lượng lớn một cách an toàn và hiệu quả.

+ **Phân tách theo miền nghiệp vụ:** Hệ thống chia thành các microservices độc lập theo ngữ cảnh (Auth, Event, Ticket, Staff, Venue) chạy trên nền tảng container Amazon ECS.
+ **Bảo mật & Phân phối:** Amazon CloudFront làm nhiệm vụ lưu trữ đệm CDN, cùng bảo vệ với AWS WAF. Các thành phần bên trong được bảo mật cấu hình trong Private Subnet và truy xuất thông qua cấu trúc API Gateway với Application Load Balancer (ALB).
+ **Xử lý Bất đồng bộ (Event-Driven):** Sử dụng hàng đợi Amazon SQS để tiếp nhận các luồng xử lý gửi PDF vé qua Amazon SES từ Notification Service, tránh tình trạng nghẽn nghẽn máy chủ.
+ **Tầng Dữ liệu mạnh mẽ:** Dữ liệu hệ thống được lưu tại Amazon RDS MySQL chạy Multi-AZ. Bộ nhớ đệm Amazon ElastiCache (Redis) giúp giảm thiểu các truy vấn cơ sở dữ liệu nặng nề.

#### Lộ trình Workshop

Trong bài thực hành này, bạn sẽ triển khai toàn bộ kiến trúc thông qua công cụ tự động hóa (Terraform) và sau đó lần lượt kiểm tra từng thành phần:
+ **Khởi tạo tài nguyên:** Triển khai hạ tầng AWS hoàn toàn tự động bằng mã nguồn Terraform.
+ **Kiểm tra Data & Messaging:** Kiểm tra kết nối và dữ liệu trong RDS, ElastiCache, hàng đợi SQS, và hệ thống gửi email SES.
+ **Kiểm tra Backend & Networking:** Thử nghiệm gọi API nội bộ qua Application Load Balancer và đảm bảo các container microservices chạy ổn định trên ECS Fargate.
+ **Kiểm tra Frontend & Edge:** Truy cập giao diện web React được lưu trữ toàn cầu qua CloudFront và xem cách AWS WAF bảo vệ mạng lưới.

![FPT Event Management Architecture](/images/2-Proposal/fpt-event-management.jpg)
