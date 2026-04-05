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
   - Truy cập giao diện AWS Console, nhập **RDS** vào thanh tìm kiếm và chọn dịch vụ **RDS**.
   
   ![Tìm kiếm dịch vụ RDS](image-1.png)
   
   - Nhấp vào mục **Databases** ở thanh công cụ bên trái để xem danh sách.
   
   ![Chọn cơ sở dữ liệu](image.png)
   
   - Xác nhận các database đã được tạo thành công với trạng thái **Available**.
   
   ![Xác nhận RDS tạo thành công](image-2.png)

2. **Amazon ElastiCache (Redis):** Xác minh Redis endpoint đã hình thành.
   - Nhập **ElastiCache** vào thanh tìm kiếm và chọn dịch vụ **ElastiCache**.
   
   ![Tìm kiếm dịch vụ Redis](image-3.png)
   
   - Chọn mục **Redis clusters** ở thanh công cụ bên.
   
   ![Chọn danh sách Redis clusters](image-4.png)
   
   - Xác nhận cluster Redis đã được tạo thành công.
   
   ![Xác nhận Redis tạo thành công](image-5.png)

3. **Amazon SQS:** Đảm bảo hàng đợi SQS đã sẵn sàng nhận tin nhắn sự kiện.
   - Nhập **SQS** vào thanh tìm kiếm và chọn dịch vụ **Simple Queue Service**.
   
   ![Tìm kiếm dịch vụ SQS](image-6.png)
   
   - Xác nhận các hàng đợi (queues) SQS đã được liệt kê đầy đủ trên giao diện.
   
   ![Xác nhận SQS tạo thành công](image-7.png)
