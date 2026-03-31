---
title: "Worklog Tuần 2"
date: 2026-01-12
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

* Cho phép EC2 trong private subnet truy cập internet an toàn qua NAT Gateway.
* Kết nối các dịch vụ AWS riêng tư không qua internet công cộng bằng VPC Endpoints.
* Kết nối nhiều VPC với nhau bằng VPC Peering.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Ôn lại cấu hình VPC tuần 1 <br> - Tìm hiểu NAT Gateway vs NAT Instance: khác biệt về chi phí, tính sẵn sàng và quản lý | 12/01/2026 | 12/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - **Thực hành:** <br>&emsp; + Tạo NAT Gateway trong public subnet <br>&emsp; + Cập nhật route table private để route 0.0.0.0/0 → NAT Gateway <br>&emsp; + Kiểm tra internet access từ EC2 private | 13/01/2026 | 13/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Tìm hiểu VPC Endpoints: Interface Endpoint vs Gateway Endpoint <br> - Hiểu use case: S3, DynamoDB (Gateway), SSM, ECR (Interface) <br> - Nghiên cứu endpoint policies | 14/01/2026 | 14/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - **Thực hành:** <br>&emsp; + Tạo Gateway Endpoint cho S3 <br>&emsp; + Truy cập S3 từ private subnet không qua internet <br>&emsp; + Tạo Interface Endpoint cho SSM & kiểm tra session manager | 15/01/2026 | 15/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Tìm hiểu VPC Peering: khái niệm, yêu cầu CIDR, cập nhật route table <br> - Hiểu giới hạn transitive peering & tổng quan AWS Transit Gateway <br> - **Thực hành:** Peer hai VPC & kiểm tra kết nối EC2 cross-VPC | 16/01/2026 | 16/01/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 2:

* Triển khai NAT Gateway và xác nhận EC2 trong private subnet có thể kết nối internet.
* Hiểu sự khác biệt về chi phí và độ bền giữa NAT Gateway và NAT Instance.
* Tạo VPC Gateway Endpoint cho S3, xác nhận traffic không đi qua internet công cộng.
* Thiết lập Interface Endpoint cho SSM và kết nối EC2 private không cần bastion host.
* Thiết lập VPC Peering thành công giữa hai VPC và cập nhật route table tương ứng.
* Hiểu hạn chế của transitive peering và khi nào nên dùng AWS Transit Gateway.
* ...
