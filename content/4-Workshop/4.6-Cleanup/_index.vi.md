---
title : "Dọn dẹp"
date : 2024-01-01 
weight : 6
chapter : false
pre : " <b> 4.6. </b> "
---

#### Dọn dẹp tài nguyên

Để tránh phát sinh chi phí hàng tháng sau khi kết thúc workshop, bạn cần thiết phải xóa toàn bộ tài nguyên đã tạo. Nhờ sử dụng Terraform, việc dọn dẹp này có thể tự động hóa rất đơn giản:

```bash
terraform destroy --auto-approve
```

**Lưu ý:** Một số tài nguyên (ví dụ: các bucket S3 chứa tệp người dùng tải lên) có thể bắt buộc phải được làm rỗng thủ công thông qua giao diện AWS Console trước khi tiến trình `destroy` có thể xóa thành công mọi thứ.