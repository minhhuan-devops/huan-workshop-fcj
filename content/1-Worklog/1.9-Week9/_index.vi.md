---
title: "Worklog Tuần 9"
date: 2026-03-02
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

* Cấu hình các integration của API Gateway: Lambda, HTTP, AWS Service và VPC Link.
* Implement Lambda Authorizers và Cognito User Pools để xác thực API.
* Kết nối API Gateway với backend service trong VPC qua VPC Link và NLB.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Ôn các loại integration API Gateway: Lambda Proxy, Lambda Custom, HTTP, AWS Service, Mock <br> - Hiểu sự khác biệt Proxy vs Non-Proxy integration (headers, body, status codes) | 02/03/2026 | 02/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - **Thực hành:** <br>&emsp; + Tạo Lambda function (Python/Node.js) <br>&emsp; + Tích hợp với API Gateway dùng Lambda Proxy integration <br>&emsp; + Test end-to-end: API GW → Lambda → response | 03/03/2026 | 03/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Tìm hiểu authorizers API Gateway: Lambda Authorizer (token/request type) vs Cognito Authorizer <br> - **Thực hành:** <br>&emsp; + Tạo Lambda Authorizer (xác thực bearer token) <br>&emsp; + Gắn vào endpoint và test với/không có token hợp lệ | 04/03/2026 | 04/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Tìm hiểu VPC Link: kết nối API Gateway với backend private (NLB trong VPC) <br> - **Thực hành:** <br>&emsp; + Tạo VPC Link trỏ đến NLB hiện có <br>&emsp; + Cấu hình HTTP_PROXY integration qua VPC Link <br>&emsp; + Xác nhận traffic ECS/EC2 private đi qua API GW | 05/03/2026 | 05/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Tìm hiểu caching API Gateway: TTL, cache invalidation, per-key caching <br> - Nghiên cứu tích hợp X-Ray tracing cho API Gateway <br> - **Thực hành:** Bật caching cho GET endpoint và đo mức cải thiện response time | 06/03/2026 | 06/03/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 9:

* Tích hợp API Gateway với Lambda function qua Lambda Proxy integration end-to-end.
* Implement Lambda Authorizer tùy chỉnh để xác thực bearer token trên các route được bảo vệ.
* Tạo VPC Link và kết nối API Gateway với service NLB private.
* Xác nhận API Gateway chuyển tiếp request đúng đến ECS container private qua VPC Link.
* Bật caching response API Gateway và quan sát giảm latency đáng kể.
* Kích hoạt AWS X-Ray tracing và phân tích service map cho chuỗi gọi API → Lambda.
* ...
