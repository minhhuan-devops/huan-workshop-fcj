---
title : "Kiểm tra Data & Messaging"
date : 2024-01-01 
weight : 3
chapter : false
pre : " <b> 4.3. </b> "
---

#### Xác minh Dữ liệu và Hàng đợi

Sau khi hoàn tất lệnh `terraform apply`, tất cả các dịch vụ nội bộ đã được khởi tạo. Trong bước này, chúng ta truy cập AWS Console để xác minh từng dịch vụ lần lượt.

---

### 1. Amazon RDS (MySQL)

Amazon RDS là dịch vụ cơ sở dữ liệu quan hệ được quản lý hoàn toàn bởi AWS — bạn không cần cài đặt hay vá lỗi máy chủ mà vẫn có đầy đủ tính năng MySQL với sao lưu tự động và khả dụng cao.

**Kiểm tra các database `auth`, `event`, `ticket`,... đã được khởi tạo thành công chưa:**

- Nhập **RDS** vào thanh tìm kiếm và chọn dịch vụ **RDS**.

![Tìm kiếm dịch vụ RDS](/4-workshop/4.3-verify-data-messaging/image-1.png)

- Nhấp vào mục **Databases** ở thanh công cụ bên trái để xem danh sách.

![Chọn cơ sở dữ liệu](/4-workshop/4.3-verify-data-messaging/image.png)

- Xác nhận các database đã được tạo với trạng thái **Available**.

![Xác nhận RDS tạo thành công](/4-workshop/4.3-verify-data-messaging/image-2.png)

---

### 2. Amazon ElastiCache (Redis)

Amazon ElastiCache là dịch vụ bộ nhớ đệm (caching) tốc độ cao, lưu trữ tạm các dữ liệu thường xuyên truy xuất để giảm tải cho RDS và trả về phản hồi trong vòng mili-giây.

**Xác minh Redis cluster đã được khởi tạo:**

- Nhập **ElastiCache** vào thanh tìm kiếm và chọn dịch vụ **ElastiCache**.

![Tìm kiếm dịch vụ ElastiCache](/4-workshop/4.3-verify-data-messaging/image-3.png)

- Chọn mục **Redis clusters** ở thanh công cụ bên trái.

![Chọn danh sách Redis clusters](/4-workshop/4.3-verify-data-messaging/image-4.png)

- Xác nhận cluster Redis đã được tạo thành công với trạng thái **Available**.

![Xác nhận Redis tạo thành công](/4-workshop/4.3-verify-data-messaging/image-5.png)

---

### 3. Amazon SQS

Amazon SQS (Simple Queue Service) là hàng đợi thông điệp giúp các microservice giao tiếp bất đồng bộ với nhau. Khi Ticket Service hoàn tất giao dịch, nó đẩy sự kiện vào SQS và Notification Service sẽ lấy ra để gửi email — hai service không cần chờ nhau, tránh nghẽn cổ chai.

**Đảm bảo các hàng đợi đã sẵn sàng nhận sự kiện:**

- Nhập **SQS** vào thanh tìm kiếm và chọn **Simple Queue Service**.

![Tìm kiếm dịch vụ SQS](/4-workshop/4.3-verify-data-messaging/image-6.png)

- Xác nhận các hàng đợi (queues) đã được liệt kê đầy đủ trên giao diện.

![Xác nhận SQS tạo thành công](/4-workshop/4.3-verify-data-messaging/image-7.png)
