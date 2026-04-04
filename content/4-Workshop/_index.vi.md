---
title: "Workshop"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 4. </b> "
---

# Thiết lập Hệ thống Quản lý Sự kiện FPT trên nền tảng AWS Microservices

![FPT Event Management Architecture](/images/2-Proposal/fpt-event-management.jpg)

#### Tổng quan

**Hệ thống Quản lý Sự kiện FPT** cung cấp một nền tảng toàn diện, có khả năng mở rộng cao để quản lý các sự kiện, phát hành vé, phân bổ nhân sự và địa điểm bằng cách áp dụng kiến trúc AWS Microservices.

Trong bài workshop này, bạn sẽ học cách xây dựng, cấu hình và triển khai một nền tảng quản lý sự kiện mạnh mẽ trên các dịch vụ được quản lý của AWS nhằm đảm bảo tính khả dụng (High Availability), bảo mật và khả năng mở rộng (Scalability) trong các đợt mở bán vé khối lượng lớn.

Hệ thống triển khai một mô hình microservices dưới dạng container:
+ **Frontend** - Lưu trữ trên Amazon S3 và phân phối toàn cầu qua Amazon CloudFront, được bảo vệ bởi AWS WAF.
+ **Định tuyến API** - Điều hướng lưu lượng an toàn thông qua Amazon Route 53, API Gateway và Application Load Balancer (ALB).
+ **Lớp Dịch vụ (Service Layer)** - Các microservices backend theo miền nghiệp vụ (Auth, Event, Ticket, Staff, Venue, Notification) được quản lý bởi Amazon ECS.
+ **Tin nhắn Bất đồng bộ (Event-Driven)** - Hàng đợi Amazon SQS đệm khối lượng công việc sự kiện, trong khi Amazon SES xử lý việc gửi email tự động.
+ **Cơ sở dữ liệu** - Amazon RDS (MySQL 8.0 Multi-AZ) lưu trữ dữ liệu an toàn và Amazon ElastiCache (Redis) tăng tốc độ truy xuất với bộ nhớ đệm.
+ **Giám sát & Lưu trữ** - Amazon CloudWatch để ghi log tập trung phục vụ giám sát và Amazon S3 dùng lưu trữ tĩnh dữ liệu hình ảnh/tài liệu.

#### Nội dung

1. [Tổng quan về workshop](4.1-Workshop-overview/)
2. [Chuẩn bị & Cài đặt](4.2-Prerequisite-and-deployment/)
3. [Kiểm tra Data & Messaging (RDS, Redis, SQS, SES)](4.3-Verify-data-messaging/)
4. [Kiểm tra Backend Microservices (ECS, ALB)](4.4-Verify-backend/)
5. [Kiểm tra Frontend & API Gateway (S3, CloudFront, WAF, API Gateway)](4.5-Verify-frontend/)
6. [Dọn dẹp tài nguyên](4.6-Cleanup/)