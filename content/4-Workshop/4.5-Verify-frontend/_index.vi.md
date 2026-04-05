---
title : "Kiểm tra Frontend & API Gateway"
date : 2024-01-01 
weight : 5
chapter : false
pre : " <b> 4.5. </b> "
---

#### Xác minh Giao diện người dùng và API Gateway

Bước cuối cùng là kiểm tra các thành phần Public Facing cho phép người dùng cuối (người nằm ngoài mạng VPC) có thể tương tác với hệ thống.

1. **Kiểm tra Amazon API Gateway:**
   - Đóng vai trò là cửa ngõ giao tiếp công khai, chúng ta cần kiểm tra cấu trúc định tuyến (routes) để đảm bảo traffic được đẩy vào trong nội bộ tới dịch vụ ALB một cách an toàn.
   - Truy cập **API Gateway** qua thanh tìm kiếm.
   
   ![Tìm kiếm API Gateway](/4-workshop/4.5-verify-frontend/image.png)
   
   - Chọn API đã được triển khai (ví dụ: `fpt-event-api`).
   
   ![Chọn API Gateway fpt-event-api](/4-workshop/4.5-verify-frontend/image-1.png)
   
   - Kiểm tra các Routes đã được cấu hình đầy đủ để trỏ tới các microservices chưa.
   
   ![Kiểm tra các Routes của API](/4-workshop/4.5-verify-frontend/image-2.png)

2. **Kiểm tra Amazon S3 & CloudFront:**
   - CloudFront Distribution sẽ phân phối giao diện trang tĩnh ReactJS được lưu trữ tại S3. Chúng ta cần lấy URL của CloudFront để có thể truy cập trang web.
   - Cụ thể, truy cập dịch vụ **CloudFront** trên trình duyệt AWS.
   
   ![Tìm kiếm CloudFront](/4-workshop/4.5-verify-frontend/image-6.png)
   
   - Click chọn vào menu **Distributions**.
   
   ![Chọn Distributions](/4-workshop/4.5-verify-frontend/image-7.png)
   
   - Trải nghiệm trang web bằng cách sao chép và đi đến đường dẫn của **Distribution domain name**.
   
   ![Lấy Tên miền URL CloudFront](/4-workshop/4.5-verify-frontend/image-8.png)
   
   - Giao diện của trang web sẽ hiển thị nếu triển khai hoạt động ổn định.
   
   ![Giao diện hệ thống ReactJS](/4-workshop/4.5-verify-frontend/image-3.png)

3. **Kiểm tra AWS WAF (Web Application Firewall):**
   - Đảm bảo tính bảo mật được thiết lập bởi lớp tường lửa WAF đối với các lưu lượng độc hại hoặc bất thường.
   - Vào dịch vụ **WAF & Shield**, chọn **Web ACLs** để đảm bảo WAF đã được tạo thành công và gắn vào CloudFront tương ứng.
   
   ![Trang WAF](/4-workshop/4.5-verify-frontend/image-4.png)
   
   ![Xác nhận cấu hình WAF](/4-workshop/4.5-verify-frontend/image-5.png)