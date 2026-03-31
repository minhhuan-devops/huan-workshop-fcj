---
title: "Worklog Tuần 1"
date: 2026-01-05
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu tuần 1:

* Làm quen với nền tảng đám mây AWS và hiểu các nhóm dịch vụ cốt lõi (Compute, Storage, Networking, Database).
* Thiết lập IAM, AWS CLI và xây dựng VPC nền tảng với public/private subnet.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Giới thiệu về AWS Cloud & tổng quan chương trình FCJ <br> - Tạo tài khoản AWS Free Tier <br> - Khám phá AWS Management Console | 05/01/2026 | 05/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Tìm hiểu hạ tầng toàn cầu AWS: Regions, AZs, Edge Locations <br> - Học IAM cơ bản: Users, Groups, Roles, Policies <br> - **Thực hành:** Tạo IAM user với chính sách least-privilege | 06/01/2026 | 06/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Cài đặt & cấu hình AWS CLI <br> - Học các khái niệm cốt lõi VPC: CIDR, Subnets (Public/Private), Route Tables, Internet Gateway <br> - Hiểu luồng traffic trong VPC | 07/01/2026 | 07/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - **Thực hành:** <br>&emsp; + Tạo VPC tùy chỉnh (10.0.0.0/16) <br>&emsp; + Thêm public subnet (10.0.1.0/24) & private subnet (10.0.2.0/24) <br>&emsp; + Gắn Internet Gateway & cấu hình route tables | 08/01/2026 | 08/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Tìm hiểu Security Groups vs NACLs (stateful vs stateless) <br> - **Thực hành:** <br>&emsp; + Khởi chạy EC2 trong public subnet <br>&emsp; + Kiểm tra các quy tắc inbound/outbound | 09/01/2026 | 09/01/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 1:

* Hiểu hạ tầng toàn cầu AWS: Regions, Availability Zones và Edge Locations.
* Tạo tài khoản AWS Free Tier và cấu hình IAM với chính sách least-privilege.
* Cài đặt và cấu hình AWS CLI với Access Key, Secret Key và Region mặc định.
* Nắm vững VPC: ký hiệu CIDR, public/private subnet, route table và Internet Gateway.
* Triển khai VPC tùy chỉnh và kiểm tra kết nối từ EC2 trong public subnet.
* Hiểu sự khác biệt giữa Security Groups (stateful) và NACLs (stateless).
* ...
