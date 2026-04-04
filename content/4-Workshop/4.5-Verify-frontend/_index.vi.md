---
title : "Kiểm tra Frontend & API Gateway"
date : 2024-01-01 
weight : 5
chapter : false
pre : " <b> 4.5. </b> "
---

#### Xác minh Giao diện người dùng và API Gateway

Bước cuối cùng là kiểm tra các thành phần Public Facing cho phép người dùng cuối tương tác với hệ thống.

1. **Amazon API Gateway:** Kiểm tra cấu trúc các tuyến (routes) đã triển khai để dẫn kết nối tới nội bộ ALB. Gọi thử API Gateway endpoint công khai để lấy dữ liệu.
2. **Amazon S3 & CloudFront:** Lấy URL của CloudFront Distribution từ output của Terraform. Truy cập bằng trình duyệt web để xem giao diện ReactJS.
3. **AWS WAF (Web Application Firewall):** Thử thực hiện một số truy vấn SQL Injection (ví dụ: `?id=1' OR '1'='1`) trên URL của CloudFront để xác minh WAF chặn lưu lượng độc hại với mã lỗi HTTP 403 Forbidden.
