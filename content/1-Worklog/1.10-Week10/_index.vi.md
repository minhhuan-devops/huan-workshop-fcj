---
title: "Worklog Tuần 10"
date: 2026-03-09
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

* Hiểu Amazon CloudFront như một mạng phân phối nội dung (CDN) toàn cầu.
* Cấu hình Origins, Behaviors, Cache Policies và Origin Access Control (OAC).
* Bảo mật và tối ưu phân phối nội dung cho static assets và dynamic APIs.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Giới thiệu CloudFront: edge locations, Points of Presence (PoPs), regional edge caches <br> - Tìm hiểu các thành phần CloudFront: Distributions, Origins, Behaviors, Cache Policies, TTL | 09/03/2026 | 09/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - **Thực hành:** <br>&emsp; + Tạo CloudFront distribution với S3 origin <br>&emsp; + Cấu hình Origin Access Control (OAC) để chặn truy cập S3 trực tiếp <br>&emsp; + Cập nhật S3 bucket policy chỉ cho phép CloudFront | 10/03/2026 | 10/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Tìm hiểu CloudFront Behaviors: path patterns, cache policies, origin request policies <br> - Cấu hình nhiều behavior: <br>&emsp; + `/api/*` → ALB/API Gateway origin (không cache) <br>&emsp; + `/*` → S3 origin (cache static assets) | 11/03/2026 | 11/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Tìm hiểu bảo mật CloudFront: bắt buộc HTTPS, chứng chỉ SSL tùy chỉnh (ACM), Geo Restriction <br> - Nghiên cứu use case CloudFront Functions vs Lambda@Edge <br> - **Thực hành:** Cấu hình chuyển hướng HTTPS và gắn chứng chỉ ACM | 12/03/2026 | 12/03/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Tìm hiểu cache invalidation và monitoring CloudFront (Cache Hit Rate, tỷ lệ lỗi 4xx/5xx) <br> - **Thực hành:** <br>&emsp; + Invalidate path pattern sau khi deploy code mới <br>&emsp; + Xem CloudWatch metrics và access logs của distribution | 13/03/2026 | 13/03/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 10:

* Hiểu kiến trúc edge CloudFront và cách PoPs giảm độ trễ cho người dùng trên toàn cầu.
* Tạo CloudFront distribution với S3 origin được bảo mật bằng Origin Access Control (OAC).
* Cấu hình routing đa behavior: static assets từ S3 (có cache) và API từ ALB (không cache).
* Bắt buộc HTTPS-only và gắn chứng chỉ SSL ACM vào distribution.
* Thực hiện cache invalidation sau deployment và theo dõi Cache Hit Ratio trong CloudWatch.
* Hiểu khi nào dùng CloudFront Functions vs Lambda@Edge dựa trên execution context.
* ...
