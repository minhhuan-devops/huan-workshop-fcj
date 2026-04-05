---
title: "Bản đề xuất"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# FPT Event Management System  
## Giải pháp Hệ thống quản lý sự kiện và bán vé trên nền tảng AWS Microservices

### 1. Tóm tắt điều hành  
Hệ thống **FPT Event Management** được thiết kế để cung cấp một nền tảng toàn diện, có khả năng mở rộng cao để quản lý các sự kiện, phát hành vé, phân bổ nhân sự và quản lý địa điểm. Áp dụng chuẩn kiến trúc Microservices trên AWS (sử dụng Amazon ECS), hệ thống đảm bảo duy trì tính khả dụng (High Availability) trong các đợt mở bán vé khối lượng lớn, tối ưu hóa việc gửi thông báo bất đồng bộ và tăng cường bảo mật từ tầng mạng cho đến dữ liệu.

### 2. Tuyên bố vấn đề  
#### Vấn đề hiện tại  
Với các sự kiện quy mô lớn, việc mở bán vé (flash sale) thường tạo ra những đợt tăng đột biến về lưu lượng truy cập (traffic spikes). Các hệ thống monolithic truyền thống dễ gặp tình trạng quá tải, nghẽn cổ chai tại cơ sở dữ liệu và khó mở rộng từng phần. Bên cạnh đó, việc gửi thông báo (email vé, nhắc nhở sự kiện) nếu thực hiện đồng bộ sẽ làm chậm phản hồi của hệ thống.

#### Giải pháp  
Áp dụng kiến trúc Microservices để tách biệt các miền nghiệp vụ (Domain): **Auth, Event, Ticket, Staff** và **Venue**. Toàn bộ dịch vụ Backend được chứa trong container (Docker) và quản lý bởi **Amazon ECS**. Frontend lưu trữ trên **Amazon S3** và phân phối qua **CloudFront CDN** kèm **AWS WAF** để chống tấn công Web. Các request API được quản lý tập trung qua **API Gateway** và phân tải bởi **ALB (Application Load Balancer)**. Việc gửi thông báo được tách riêng thành **Notification Service** xử lý bất đồng bộ thông qua hàng đợi **Amazon SQS** và gửi email bằng **Amazon SES**. Dữ liệu được lưu trữ trên **Amazon RDS (MySQL 8.0 Multi-AZ)** để đảm bảo tính an toàn và **ElastiCache (Redis)** để tăng tốc độ truy xuất.

#### Lợi ích và ROI  
- **Khả năng mở rộng:** Dễ dàng scale-out riêng lẻ service "Ticket" khi có đợt bán vé mà không ảnh hưởng tới các service khác.
- **Tính khả dụng cao:** RDS Multi-AZ và kiến trúc container đảm bảo hệ thống không bị gián đoạn.
- **Trải nghiệm người dùng:** Tốc độ tải trang nhanh nhờ CloudFront, mượt mà và không lo sập web.
- Sự đầu tư ban đầu cho kiến trúc Microservices mang lại hiệu quả dài hạn, giảm thiểu tối đa rủi ro thiệt hại do gián đoạn hệ thống.

**Lưu trình vận hành (Event Lifecycle)**  
Hệ thống bao phủ toàn bộ vòng đời của một sự kiện:
- **Ban tổ chức (Organizer)** gửi yêu cầu tổ chức sự kiện và đặt chỗ khu vực địa điểm (venue).
- **Quản trị viên (Admin)** phê duyệt yêu cầu và hệ thống mở bán vé.
- **Sinh viên (Student)** tiến hành mua vé thông qua Ví điện tử (Wallet) hoặc VNPay.
- **Hệ thống** tự động phát hành vé dưới dạng tệp PDF kèm mã QR và gửi email thông báo.
- **Nhân viên (Staff)** quét mã QR tại quầy check-in và tự động cập nhật báo cáo điểm danh.

**Mục tiêu thiết kế (Design Targets)**  
- **Tính toàn vẹn dữ liệu cao (High data integrity):** Đặc biệt là cho các luồng thanh toán và luồng cấp phát vé.
- **Khả năng xử lý đồng thời tốt (Good concurrency behavior):** Đảm bảo hệ thống ổn định trong cùng một thời điểm có lượng lớn người truy cập mua vé đồng loạt.
- **Tối ưu hóa lưu trữ và vận hành rõ ràng:** Giảm thiểu lãng phí không gian lưu trữ (low storage waste) và phân định quyền sở hữu vận hành (operational ownership) minh bạch.

### 3. Kiến trúc giải pháp  
Hệ thống tận dụng sức mạnh của các dịch vụ Managed Services trên AWS, kết hợp bảo mật sâu nhiều lớp và bất đồng bộ hóa các tác vụ trễ cao.

![FPT Event Management Architecture](/images/2-Proposal/fpt-event-management.jpg)

**Các dịch vụ AWS sử dụng**  
- **Amazon Route 53 & CloudFront**: Dịch vụ DNS và CDN giúp phân phối nội dung Frontend tĩnh (lưu trữ trên **S3**) tới người dùng toàn cầu với độ trễ thấp nhất.
- **AWS WAF**: Tường lửa bảo vệ ứng dụng Web, ngăn chặn các tấn công phổ biến (như SQL Injection, XSS) và giới hạn request (Rate Limiting).
- **Amazon API Gateway & ALB**: Khởi tiếp nhận API request từ người dùng, thực hiện điều hướng an toàn qua Load Balancer đến cụm ECS.
- **Amazon ECS (Elastic Container Service)**: Quản lý và vận hành các Microservices (Auth, Ticket, Event, Staff, Venue, Notification).
- **Amazon RDS (MySQL 8.0 Multi-AZ) & ElastiCache (Redis)**: Cung cấp Database quan hệ độ sẵn sàng cao và hệ thống caching bộ nhớ đệm giảm tải database.
- **Amazon SQS & Amazon SES**: Hàng đợi tin nhắn phục vụ kiến trúc Event-Driven, kết hợp SES để gửi Email tự động.
- **Amazon S3 (Storage)**: Lưu trữ các tệp tin hình ảnh sự kiện, hóa đơn PDF.
- **Amazon CloudWatch**: Ghi log, giám sát tài nguyên và hiệu suất cho toàn hệ thống.

### 4. Triển khai kỹ thuật  
**Các giai đoạn triển khai**  
1. **Thiết kế & Provisioning (IAC):** Thiết kế mô hình Database, sơ đồ mạng VPC. Sử dụng Terraform hoặc AWS CloudFormation (CDK) để viết mã hạ tầng (IaC) tự động hóa tạo tài nguyên mạng, ECS Cluster, ALB và RDS.
2. **Phát triển Microservices:** Chia nhóm code thành các repository riêng biệt cho Frontend và từng Backend Service. Cấu hình Dockerfile cho mỗi service.
3. **Triển khai luồng CI/CD:** Sử dụng GitHub Actions để tự động build Docker Image, đẩy lên ECR và cập nhật ECS Task Definitions.
4. **Tích hợp & Kiểm thử tải (Load Testing):** Tích hợp Frontend qua API Gateway. Giả lập các đợt mua vé lớn để kiểm tra khả năng bắt lỗi của WAF và khả năng mở rộng (Auto Scaling) của ECS, ElastiCache.

**Yêu cầu kỹ thuật**  
- **Frontend**: Sử dụng thư viện ReactJS, build dạng tĩnh (Static Export) để lưu trữ hoàn toàn trên S3.
- **Backend Services**: Lập trình bằng ngôn ngữ Golang. Mỗi container phải tuân thủ chuẩn Stateless để dễ điều phối.
- **Bảo mật**: Các liên kết giữa service bên trong VPC không được xuất bản ra public internet mạng. RDS & ElastiCache phải thuộc Private Subnets.

### 5. Chiến lược DevSecOps và Quy trình Kiểm thử Bảo mật
Hệ thống áp dụng tư duy bảo mật từ sớm (Shift-Left Security), lồng ghép các khâu kiểm tra an toàn thông tin ngay từ bước viết mã cho đến khi triển khai lên đám mây. Đội ngũ dự án được phân tách rõ ràng thành 3 vai trò độc lập để đảm bảo tính khách quan: Lập trình viên (Dev), Quản trị Hạ tầng (DevOps), và Chuyên gia Kiểm thử Xâm nhập (Pentester).

Quy trình DevSecOps được chia làm 3 giai đoạn (Phases) cốt lõi:

* **Phase 1: Kiểm thử Ứng dụng Cục bộ:**
    * Tiến hành rà quét mã nguồn và kiểm thử động (DAST) trên môi trường Docker nội bộ.
    * Tập trung phát hiện các lỗ hổng logic nghiệp vụ, xác thực, và cấu hình mạng nội bộ theo tiêu chuẩn OWASP Top 10.
* **Phase 1.5: Nghiệm thu và Vá lỗi (Remediation & Secure Coding):**
    * Lập trình viên (Dev) tiếp nhận báo cáo bảo mật, tiến hành vá lỗi trực tiếp tại tầng mã nguồn.
    * Áp dụng các tiêu chuẩn an toàn như thuật toán băm Bcrypt, bảo vệ JWT bằng HttpOnly Cookies, và cơ chế xác thực nội bộ (Internal Token) cho Microservices.
* **Phase 2: Kiểm thử Hạ tầng Đám mây (Cloud Infrastructure Pentest):**
    * Đánh giá bảo mật sau khi DevOps triển khai hệ thống lên AWS bằng Terraform (IaC).
    * Tập trung kiểm toán bảo mật vành đai: Rà soát cấu hình mạng Amazon VPC, siết chặt tường lửa Security Group cho Amazon RDS, loại bỏ Bastion Host, và thiết lập Rate Limiting trên AWS WAF/CloudFront để phòng chống tấn công cạn kiệt tài chính (EDoS).

### 6. Lộ trình & Mốc triển khai  
- **Tháng 1**: Khảo sát và thiết kế chi tiết Data Model, viết IaC để khởi tạo VPC, Database, và cấu trúc hạ tầng cơ bản.
- **Tháng 2**: Build và Deploy Frontend tĩnh lên S3 + CloudFront. Phát triển các core backend services (Auth, Event, Ticket) trên ECS. Thực hiện Phase 1 Pentest trên môi trường Local và Phase 1.5 Vá lỗi mã nguồn.
- **Tháng 3**: Hoàn thiện các services phụ trợ (Venue, Staff), cấu hình SQS + SES gửi mail, tích hợp toàn bộ hệ thống qua API Gateway. Đưa vào triển khai thực tế. Thực hiện Phase 2 Pentest rà soát hạ tầng AWS (Cloud Security). Chạy Load Test và đưa vào triển khai thực tế.

### 7. Ước tính ngân sách

**Chi phí hạ tầng**
- Compute (Amazon ECS với Fargate): 35,00 USD/tháng (6 microservices tối thiểu).
- Database (Amazon RDS MySQL Multi-AZ): 34,00 USD/tháng (db.t3.micro).
- Caching (Amazon ElastiCache Redis): 12,00 USD/tháng (cache.t3.micro).
- Networking (ALB, API Gateway, CloudFront, Route53): 20,00 USD/tháng.
- Bảo mật Web (AWS WAF): 6,00 USD/tháng (1 Web ACL cơ bản).
- Storage & Messaging (S3, SQS, SES, CloudWatch): 2,00 USD/tháng.

**Tổng:** 109,00 USD/tháng, 1.308 USD/12 tháng

### 8. Đánh giá rủi ro
**Ma trận rủi ro**

- Dữ liệu mâu thuẫn giữa các microservices: Ảnh hưởng cao, xác suất trung bình.
- Quá tải cục bộ luồng thanh toán: Ảnh hưởng cao, xác suất thấp.
- Chi phí AWS vượt kiểm soát: Ảnh hưởng trung bình, xác suất thấp.
- Rò rỉ thông tin nhạy cảm/mật khẩu trong mã nguồn hạ tầng (IaC): Ảnh hưởng rất cao, xác suất trung bình.
- Tấn công cạn kiệt tài chính (EDoS) bằng lưu lượng ảo: Ảnh hưởng cao, xác suất trung bình.

**Chiến lược giảm thiểu**

- Dữ liệu: Sử dụng mô hình Saga Pattern hoặc Event-driven thông qua SQS.
- Thanh toán: Áp dụng cơ chế queue bất đồng bộ và Auto-scaling tự động.
- Chi phí: Cài đặt cảnh báo ngân sách AWS Budgets, thiết lập max-capacity.
- Bảo mật cấu hình: Tuyệt đối không hardcode mật khẩu, tích hợp AWS Secrets Manager vào luồng CI/CD.
- Phòng chống EDoS: Áp dụng ranh giới vi mô (Micro-segmentation) cho Security Groups và cấu hình Targeted Rate Limiting trên AWS WAF.

**Kế hoạch dự phòng**

- Quay về quy trình mua vé, check-in thủ công nếu hạ tầng gặp sự kiện down-time.
- Sử dụng Terraform (IaC) để nhanh chóng khôi phục lại cấu hình môi trường.

### 9. Kết quả kỳ vọng
Cải tiến kỹ thuật: Tự động hóa hoàn toàn luồng phát hành vé và xử lý thanh toán, chịu tải tốt các đợt mở bán vé đồng thời lớn.
Giá trị dài hạn: Nền tảng lõi vững chắc, dễ bảo trì, có thể tái sử dụng dưới dạng SaaS cho các sự kiện khác trong tương lai của FPT.