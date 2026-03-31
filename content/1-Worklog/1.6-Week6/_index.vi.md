---
title: "Worklog Tuần 6"
date: 2026-02-09
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

* Hiểu các khái niệm container hóa với Docker và cách container khác với VM.
* Học cách build, tag và push Docker image lên Amazon Elastic Container Registry (ECR).
* Thiết lập ECR repository và tích hợp với xác thực IAM.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Giới thiệu container hóa: Docker vs Virtual Machines <br> - Tìm hiểu các khái niệm Docker cốt lõi: images, containers, layers, Dockerfile, volumes, networks | 09/02/2026 | 09/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - **Thực hành:** <br>&emsp; + Viết Dockerfile cho ứng dụng Node.js/Python <br>&emsp; + Build image: `docker build` <br>&emsp; + Chạy container: `docker run` <br>&emsp; + Kiểm tra layers với `docker inspect` | 10/02/2026 | 10/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Tìm hiểu Amazon ECR: repository private vs public, image scanning, lifecycle policies <br> - Hiểu xác thực ECR với `aws ecr get-login-password` | 11/02/2026 | 11/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - **Thực hành:** <br>&emsp; + Tạo ECR repository private <br>&emsp; + Xác thực Docker với ECR <br>&emsp; + Tag & push image lên ECR <br>&emsp; + Bật tính năng quét lỗ hổng image | 12/02/2026 | 12/02/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Tìm hiểu ECR lifecycle policies (xóa image untagged cũ) <br> - Học Docker multi-stage build để giảm kích thước image <br> - **Thực hành:** Implement Dockerfile multi-stage và so sánh kích thước image | 13/02/2026 | 13/02/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 6:

* Hiểu cách Docker container khác VM về cách ly và sử dụng tài nguyên.
* Viết Dockerfile và build container image hoạt động cho ứng dụng web.
* Tạo ECR repository private và push image đã tag thành công.
* Bật ECR image scanning và xem xét kết quả phát hiện lỗ hổng.
* Áp dụng ECR lifecycle policies để tự động xóa image untagged cũ.
* Implement multi-stage Docker build để tạo image nhẹ cho môi trường production.
* ...
