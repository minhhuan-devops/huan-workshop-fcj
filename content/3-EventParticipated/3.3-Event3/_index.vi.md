---
title: "Event 3"
date: 2026-01-29
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

## Bài thu hoạch "AWS re:Invent 2025 – Kiến trúc hiện đại hóa ứng dụng & GenAI"

### Mục đích sự kiện

- Cập nhật các announcement quan trọng từ AWS re:Invent 2025 (Nova models, Trainium3 UltraServers, AI agents, GenAI, modernization, data...).
- Giúp người tham dự hiểu các best practice về hiện đại hóa ứng dụng, kiến trúc microservices, event-driven, serverless/container và AI-driven development.
- Tạo cơ hội networking giữa AWS experts, partners và cộng đồng cloud/AI tại Việt Nam.

### Diễn giả

- **AWS speakers**: Các Solution Architect và Specialist từ AWS Vietnam chia sẻ về kiến trúc hiện đại, GenAI và kinh nghiệm triển khai thực tế.
- **Customer/Partner speakers**: Đại diện từ các doanh nghiệp và đối tác AWS tại Việt Nam chia sẻ case study chuyển đổi từ legacy monolith sang microservices, áp dụng event-driven và AI trên AWS.

### Nội dung nổi bật

#### Nhược điểm kiến trúc legacy

- Ứng dụng nguyên khối (monolith) khó mở rộng theo từng module, mỗi lần release phải build và deploy cả hệ thống, tăng rủi ro và downtime.
- Technology lock-in khiến khó áp dụng công nghệ mới như serverless, containers, GenAI và real-time data.
- Độ tin cậy thấp — một lỗi nhỏ có thể ảnh hưởng toàn bộ hệ thống, khó triển khai blue/green hay canary deployment.

#### Microservices Architecture

- Chia ứng dụng thành các service nhỏ, độc lập, có thể scale và deploy riêng, phù hợp CI/CD nhanh hơn.
- Cho phép chọn công nghệ phù hợp từng service (polyglot), dễ tích hợp AI, streaming, event-driven.
- Trên AWS thường kết hợp Amazon ECS/EKS/Lambda, API Gateway, Service Discovery và observability stack (CloudWatch, X-Ray).

#### Event-Driven Architecture

- Sử dụng events để loose coupling giữa services, hệ thống linh hoạt và dễ mở rộng.
- Trên AWS phổ biến là Amazon EventBridge, SNS/SQS, Kinesis cho real-time analytics và integration.
- Phù hợp cho các quy trình nghiệp vụ phức tạp (order, payment, notification, audit log) và streaming data.

#### Compute Evolution

- Hành trình từ EC2 truyền thống sang containers (ECS/EKS), serverless (Lambda, Fargate) và optimized instance như Trainium3 UltraServers.
- Mục tiêu tối ưu chi phí, auto-scale, giảm effort vận hành để team tập trung vào logic nghiệp vụ.

#### Amazon Q Developer

- AI assistant cho developer, tích hợp IDE và AWS console, hỗ trợ sinh code, refactor, tạo test và gợi ý kiến trúc.
- Tăng tốc hiện đại hóa bằng cách phân tích code legacy, đề xuất migration path và tự động hóa infrastructure as code.

### Bài học rút ra

- **Tư duy thiết kế cloud-native first**: Ưu tiên decoupling, elasticity, fault-tolerance, automation thay vì chỉ "lift-and-shift" từ on-prem.
- **Domain-Driven Design**: Tách bounded context rõ ràng trước khi chuyển sang microservices và event-driven.
- **Kiến trúc kết hợp**: Microservices + event-driven + serverless/containers + managed data services (Aurora, DynamoDB, streaming, vector DB).
- **Resilience patterns**: Circuit breaker, retry, backoff, idempotency; observability end-to-end và security by design.
- **Phased migration**: Blue/green deployment, feature flags để giảm rủi ro khi migrate từng phần thay vì big-bang rewrite.

### Ứng dụng vào công việc

- Áp dụng tư duy decomposition: tách monolith thành các domain rõ ràng, đề xuất kiến trúc microservices hoặc modular monolith.
- Chọn AWS services phù hợp (API Gateway + Lambda cho POC, ECS/EKS cho production), kết hợp event-driven bằng SQS/EventBridge.
- Bắt đầu dùng Amazon Q Developer trong development workflow để hỗ trợ viết code, test, refactor.

### Một số hình ảnh sự kiện

**Toàn cảnh venue và session khai mạc**

![Toàn cảnh venue sự kiện](/images/3-EventParticipated/3.3-Event3/reInvent_RECAP_1.jpg)

**Check-in Session #1**

![Check-in Session 1](/images/3-EventParticipated/3.3-Event3/reInvent_RECAP_2.jpg)

**Check-in Session #2**

![Check-in Session 2](/images/3-EventParticipated/3.3-Event3/reInvent_RECAP_3.jpg)

**Bài phát biểu về Machine Learning & AI Innovation #1**

![Bài phát biểu AWS ML & AI Innovation 1](/images/3-EventParticipated/3.3-Event3/reInvent_RECAP_4.jpg)

**Bài phát biểu về Machine Learning & AI Innovation #2**

![Bài phát biểu AWS ML & AI Innovation 2](/images/3-EventParticipated/3.3-Event3/reInvent_RECAP_5.jpg)

**Đầu năm mới tại AWS — sẵn sàng cho những thử thách mới**

![Nụ cười ngày đầu năm tại AWS](/images/3-EventParticipated/3.3-Event3/reInvent_RECAP_6.jpg)

**Chụp ảnh đồng đội và kết thúc event**

![Hình chụp đồng đội](/images/3-EventParticipated/3.3-Event3/reInvent_RECAP_7.jpg)

---

## Tổng kết

Sự kiện nhấn mạnh tầm quan trọng của tư duy kiến trúc hiện đại, chiến lược migration thực tế và vai trò các dịch vụ AWS trong việc xây dựng ứng dụng scalable, secure và có khả năng AI.
