---
title : "Kiểm tra Frontend & API Gateway"
date : 2024-01-01 
weight : 5
chapter : false
pre : " <b> 4.5. </b> "
---

#### Xác minh Giao diện người dùng và API Gateway

Bước này kiểm tra các thành phần tiếp xúc trực tiếp với người dùng cuối (Public Facing) — những thứ mà người dùng bên ngoài mạng VPC có thể truy cập được.

---

### 1. Amazon API Gateway

Amazon API Gateway là "cửa ngõ" duy nhất tiếp nhận mọi yêu cầu API từ Internet vào hệ thống backend. Nó cung cấp cơ chế giới hạn tốc độ gọi (rate-limiting), bảo mật và định tuyến đúng đến từng microservice nội bộ.

**Kiểm tra các Routes đã được cấu hình đầy đủ:**

- Nhập **API Gateway** vào thanh tìm kiếm và chọn dịch vụ.

![Tìm kiếm API Gateway](/4-workshop/4.5-verify-frontend/image.png)

- Chọn API đã được triển khai (ví dụ: `fpt-event-api`).

![Chọn API fpt-event-api](/4-workshop/4.5-verify-frontend/image-1.png)

- Kiểm tra các Routes để đảm bảo đã được cấu hình đầy đủ trỏ tới các microservice.

![Kiểm tra Routes của API Gateway](/4-workshop/4.5-verify-frontend/image-2.png)

---

### 2. Amazon S3 & CloudFront

Amazon S3 là kho lưu trữ đối tượng dùng để host các file tĩnh của Frontend ReactJS. Amazon CloudFront là mạng phân phối nội dung (CDN) toàn cầu — nó cache các file tĩnh từ S3 tại các điểm phân phối (edge location) gần người dùng nhất để trang web tải nhanh hơn đáng kể.

**Lấy URL của CloudFront để truy cập trang web:**

- Nhập **CloudFront** vào thanh tìm kiếm và chọn dịch vụ.

![Tìm kiếm CloudFront](/4-workshop/4.5-verify-frontend/image-6.png)

- Chọn **Distributions** từ menu bên trái.

![Chọn Distributions](/4-workshop/4.5-verify-frontend/image-7.png)

- Sao chép **Distribution domain name** và mở trên trình duyệt để truy cập trang web.

![Lấy Domain Name của CloudFront](/4-workshop/4.5-verify-frontend/image-8.png)

- Giao diện ReactJS hiển thị thành công xác nhận toàn bộ hệ thống hoạt động ổn định.

![Giao diện trang web ReactJS](/4-workshop/4.5-verify-frontend/image-3.png)

---

### 3. AWS WAF (Web Application Firewall)

AWS WAF là tường lửa ứng dụng web chuyên nhận diện và chặn các lưu lượng độc hại — như tấn công SQL Injection, XSS — ngay tại lớp CloudFront trước khi chúng chạm đến hệ thống backend.

**Xác nhận WAF đã gắn vào CloudFront:**

- Nhập **WAF & Shield** vào thanh tìm kiếm và chọn **Web ACLs**.

![Trang WAF & Shield](/4-workshop/4.5-verify-frontend/image-4.png)

- Xác nhận Web ACL đã được tạo và gắn (associated) đúng vào CloudFront Distribution.

![Xác nhận cấu hình WAF trên CloudFront](/4-workshop/4.5-verify-frontend/image-5.png)