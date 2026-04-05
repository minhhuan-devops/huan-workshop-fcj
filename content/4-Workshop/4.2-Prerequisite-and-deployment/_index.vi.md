---
title : "Chuẩn bị và Triển khai"
date : 2024-01-01 
weight : 2
chapter : false
pre : " <b> 4.2. </b> "
---

Để thực hành workshop này, bạn cần cài đặt các công cụ sau:

### 1. Cài đặt AWS CLI

AWS Command Line Interface (AWS CLI) là một công cụ hợp nhất để quản lý các dịch vụ AWS. 

#### Windows
Tải file cài đặt MSI và chạy:
[Tải AWS CLI cho Windows](https://awscli.amazonaws.com/AWSCLIV2.msi)

#### macOS
Sử dụng Homebrew:
```bash
brew install awscli
```
Hoặc tải bộ cài chuẩn:
```bash
curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
sudo installer -pkg AWSCLIV2.pkg -target /
```

#### Linux
Cài đặt qua dòng lệnh:
```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

Kiểm tra cài đặt:
```bash
aws --version
```

### 2. Cấu hình AWS CLI

Sau khi cài đặt xong, bạn cần cấu hình credentials để Terraform có thể tương tác với AWS, chạy lệnh sau:
```bash
aws configure
```
Nhập các thông tin `AWS Access Key ID`, `AWS Secret Access Key`, `Default region name` (nhập `us-east-1` hoặc `ap-southeast-1` tùy mục đích của bạn), và `Default output format` (nhập `json`).

### 3. Cài đặt Terraform

Terraform là công cụ Infrastructure as Code (IaC) để định nghĩa, cấp phát và quản lý cơ sở hạ tầng.

#### Windows
Sử dụng Chocolatey:
```bash
choco install terraform
```
Hoặc tải trực tiếp file zip từ [trang chủ Terraform](https://developer.hashicorp.com/terraform/downloads) và thêm đường dẫn file thực thi vào môi trường (Environment Variables).

#### macOS
Sử dụng Homebrew:
```bash
brew tap hashicorp/tap
brew install hashicorp/tap/terraform
```

#### Linux (Ubuntu/Debian)
```bash
wget -O- https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install terraform
```

Kiểm tra cài đặt:
```bash
terraform --version
```

### 4. Git và trình soạn thảo
- **Git:** Dùng để clone mã nguồn workshop.
- **Visual Studio Code (VS Code):** Môi trường để viết và chỉnh sửa code (khuyên dùng). Cài đặt thêm Extension `HashiCorp Terraform` để hỗ trợ hiển thị code Terraform tốt hơn.

### 5. Triển khai kiến trúc với Terraform

Sau khi đã cài đặt tất cả các công cụ cần thiết, bạn hãy clone mã nguồn về và chạy các lệnh dưới đây để tự động triển khai toàn bộ hệ thống:

```bash
git clone https://github.com/FPT-EVENT-MANAGEMENT-OJT/FPT_EVENT_MANAGEMENT_Microservices.git
cd FPT_EVENT_MANAGEMENT_Microservices/infrastructure
terraform init
terraform plan
terraform apply --auto-approve
```

Quá trình này có thể mất từ 15 - 20 phút do phải khởi tạo cấu hình lưu trữ, RDS, ElastiCache, ALB, và các cụm container Fargate.