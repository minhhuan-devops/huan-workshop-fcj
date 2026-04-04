---
title : "Kiểm tra Data & Messaging"
date : 2024-01-01 
weight : 3
chapter : false
pre : " <b> 4.3. </b> "
---

#### Xác minh Dữ liệu và Hàng đợi

Sau khi hoàn tất lệnh `terraform apply`, tất cả các dịch vụ nội bộ đã được khởi tạo. Trong bước này, chúng ta sẽ kết nối vào môi trường nội bộ để xác minh:

1. **Amazon RDS (MySQL):** Kiểm tra xem các cơ sở dữ liệu `auth`, `event`, `ticket`,... đã được khởi tạo thành công chưa.
2. **Amazon ElastiCache (Redis):** Xác minh Redis endpoint và khả năng kết nối.
3. **Amazon SQS & SES:** Đảm bảo hàng đợi SQS đã sẵn sàng nhận tin nhắn sự kiện và dịch vụ SES đã được xác minh email người gửi.

Bạn có thể tạo một EC2 Bastion Host (nếu cần) hoặc sử dụng Session Manager để truy cập vào vùng mạng Private Subnet nhằm thực hiện các bước kiểm tra này.