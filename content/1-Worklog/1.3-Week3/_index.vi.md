---
title: "Worklog Tuần 3"
date: 2026-01-19
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* Hiểu các loại EC2 instance, tùy chọn mua và quản lý vòng đời.
* Tạo và quản lý Amazon Machine Images (AMI) như template máy chủ tái sử dụng.
* Làm việc với Amazon EBS: loại volume, snapshot, mã hóa và thay đổi kích thước.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Học các họ EC2 instance: General Purpose (t/m), Compute (c), Memory (r/x), Storage (i/d) <br> - So sánh giá On-Demand vs Reserved vs Spot vs Savings Plans | 19/01/2026 | 19/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Tìm hiểu AMI: public, private và AWS Marketplace AMIs <br> - Hiểu vòng đời AMI: tạo, chia sẻ, sao chép sang region khác <br> - **Thực hành:** Khởi chạy EC2 với user data bootstrap script | 20/01/2026 | 20/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - **Thực hành:** <br>&emsp; + Cấu hình EC2 instance (cài Nginx, thiết lập trang web) <br>&emsp; + Tạo custom AMI từ instance đang chạy <br>&emsp; + Khởi chạy instance mới từ custom AMI và kiểm tra | 21/01/2026 | 21/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Tìm hiểu loại EBS volume: gp3, io2 Block Express, st1, sc1 <br> - Hiểu EBS Multi-Attach, mã hóa (KMS) và Lifecycle Manager <br> - Nghiên cứu sự đánh đổi giữa EBS và Instance Store | 22/01/2026 | 22/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - **Thực hành:** <br>&emsp; + Gắn & format EBS gp3 volume mới vào EC2 <br>&emsp; + Tạo EBS snapshot và khôi phục sang volume mới <br>&emsp; + Mở rộng volume online (không cần downtime) | 23/01/2026 | 23/01/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 3:

* Hiểu các họ EC2 instance và chọn đúng loại cho từng workload.
* So sánh On-Demand, Reserved, Spot và Savings Plans để tìm chiến lược tiết kiệm chi phí.
* Tạo custom AMI từ EC2 đã cấu hình và khởi chạy server giống hệt từ đó.
* Gắn, format và mount EBS volume; mở rộng volume không gián đoạn.
* Tạo EBS snapshot và khôi phục dữ liệu thành công sang volume mới.
* Hiểu sự khác biệt giữa EBS (persistent) và Instance Store (ephemeral).
* ...
