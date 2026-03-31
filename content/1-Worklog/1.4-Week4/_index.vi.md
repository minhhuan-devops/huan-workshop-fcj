---
title: "Worklog Tuần 4"
date: 2026-01-26
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

* Hiểu các tính năng EC2 nâng cao: placement groups, metadata và các mô hình truy cập an toàn.
* Tạo Launch Templates và triển khai Auto Scaling Groups (ASG) với dynamic scaling policy.
* Thiết kế kiến trúc tự phục hồi, chịu lỗi bằng ASG lifecycle hooks.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Tìm hiểu EC2 placement groups: Cluster (độ trễ thấp), Spread (cách ly lỗi), Partition (workloads phân tán) <br> - Học Enhanced Networking (ENA) và lợi ích hiệu suất | 26/01/2026 | 26/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Tìm hiểu EC2 Instance Metadata Service v2 (IMDSv2) và User Data <br> - **Thực hành:** <br>&emsp; + Truy vấn instance metadata qua IMDSv2 (dựa trên token) <br>&emsp; + Dùng User Data để bootstrap Nginx khi khởi chạy | 27/01/2026 | 27/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Tìm hiểu Launch Templates vs Launch Configurations (lý do ưu tiên LT) <br> - **Thực hành:** Tạo Launch Template với: AMI, instance type, SG, key pair, user data và tags | 28/01/2026 | 28/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - **Thực hành:** <br>&emsp; + Tạo Auto Scaling Group dùng Launch Template <br>&emsp; + Cấu hình min=1, max=4, desired=2 trên nhiều AZ <br>&emsp; + Thiết lập Target Tracking Scaling Policy (CPU 50%) | 29/01/2026 | 29/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Tìm hiểu ASG lifecycle hooks (sự kiện launching & terminating) <br> - **Thực hành:** <br>&emsp; + Mô phỏng instance lỗi và quan sát ASG tự thay thế <br>&emsp; + Tạo tải CPU và xem sự kiện scale-out <br>&emsp; + Xem lịch sử scaling activity | 30/01/2026 | 30/01/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 4:

* Hiểu chiến lược EC2 placement group và ảnh hưởng đến độ trễ và cách ly lỗi.
* Truy vấn instance metadata an toàn bằng xác thực dựa trên token IMDSv2.
* Tạo Launch Template có version với đầy đủ tham số cấu hình instance.
* Triển khai ASG trên nhiều AZ với target tracking scaling dựa trên CPU utilization.
* Xác nhận ASG tự động thay thế instance bị xóa để duy trì desired capacity.
* Quan sát và phân tích sự kiện scale-out qua CloudWatch metrics và ASG activity logs.
* ...
