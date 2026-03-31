---
title: "Worklog Tuần 8"
date: 2026-02-23
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Hiểu Amazon API Gateway và sự khác biệt giữa REST API và HTTP API.
* Cấu hình endpoints, methods, stages và cài đặt deployment.
* Bảo mật API với API keys, usage plans và resource policies.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Giới thiệu API Gateway: REST API vs HTTP API vs WebSocket API <br> - Tìm hiểu các khái niệm cốt lõi: Resources, Methods, Stages, Deployments, Throttling <br> - Hiểu API Gateway vs ALB như API front door | 23/02/2026 | 23/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - **Thực hành:** <br>&emsp; + Tạo REST API với resource GET /hello <br>&emsp; + Dùng Mock integration để trả về response tĩnh <br>&emsp; + Deploy lên stage `dev` và test với curl | 24/02/2026 | 24/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Tìm hiểu ánh xạ request/response của API Gateway: Method Request, Integration Request, Method Response <br> - Học Mapping Templates (VTL) để biến đổi request <br> - Cấu hình CORS headers | 25/02/2026 | 25/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Tìm hiểu bảo mật API Gateway: API Keys + Usage Plans, Resource Policies, IAM authorization <br> - **Thực hành:** <br>&emsp; + Tạo API Key và Usage Plan với rate limiting <br>&emsp; + Gắn key vào stage và kiểm tra response khi bị throttle | 26/02/2026 | 26/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Tìm hiểu stages và chiến lược deployment API Gateway <br> - Học stage variables và canary deployments <br> - **Thực hành:** Cấu hình hai stage (dev/prod) với throttle khác nhau và stage variables | 27/02/2026 | 27/02/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 8:

* Hiểu sự khác biệt giữa REST API, HTTP API và WebSocket API trong API Gateway.
* Tạo và deploy REST API với mock integration lên stage có tên.
* Cấu hình CORS và mapping template request/response bằng VTL.
* Implement xác thực API Key với Usage Plans và xác nhận hành vi throttling.
* Thiết lập stage deployment dev và prod với cấu hình riêng biệt bằng stage variables.
* ...
