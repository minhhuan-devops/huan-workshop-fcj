---
title: "Event 4"
date: 2026-04-04
weight: 4
chapter: false
pre: " <b> 3.4. </b> "
---

## 1. Elixir as a Unified Solution for Highly Concurrent & Fault-Tolerant DevOps Infrastructure

### Mục tiêu sự kiện

- Giới thiệu **Elixir** và mô hình **lập trình hàm** (functional programming) trên **BEAM VM**.
- Hiểu cách **Elixir** đạt được **fault-tolerance** cao thông qua **OTP** và **process supervision**.
- Ứng dụng **Elixir** vào **DevOps pipeline** như một unified toolset.

### Diễn giả

- **Nguyen Ta Minh Triet** — R&D Member tại ITea Lab, SAP Developer Intern tại Bosch GSV
  - Sinh viên năm 3 Swinburne, chuyên ngành Computer Science / Software Development
  - Đã xuất bản 2 bài conference về Elixir (CCIOT 2025, SCI 2026)
  - FCJ member và contributor tại ITea Lab

### Nội dung nổi bật

- **BEAM VM** — nền tảng giống Erlang nhưng có syntax gần Ruby.
- **BEAM Process**: các process nhẹ, không chia sẻ memory, hỗ trợ hàng triệu concurrent processes.
- **"Let It Crash" philosophy** — supervisor tự restart process thay vì dùng try/catch.
- **Hot Code Upgrades** — nâng cấp hệ thống mà không cần downtime.
- **Unified toolset** — một ngôn ngữ cho testing, deployment, monitoring.
- **Case study thực tế**: từ AWS Lambda → Elixir, giảm chi phí từ **$30K/tháng xuống $397/tháng**.

### Bài học rút ra

- **Design Mindset**: functional & immutable architecture.
- **Technical Architecture**: process-based concurrency với supervision trees mạnh mẽ.
- **Modernization Strategy**: thay thế serverless bằng BEAM để tối ưu chi phí và fault tolerance.
- Demo với **2M+ WebSocket connections** trên một single server.

### Ứng dụng

- Áp dụng **"Let It Crash"** để đơn giản hóa error handling trong distributed system.
- Cân nhắc **BEAM/Elixir** cho các service yêu cầu high concurrency (IoT, WebSocket, streaming real-time).
- Tối ưu chi phí cloud bằng cách migrate từ serverless sang **Elixir** cho các workload phù hợp.

### Trải nghiệm

- Live demo **Elixir IoT Edge Server** chạy trên Docker.
- Hands-on **concurrent processing** và **OTP supervision trees**.
- Real-world performance: **2M WebSocket connections** trên một single server.

---

## 2. Architecting for the Cloud with Kubernetes

### Mục tiêu sự kiện

- Hiểu vấn đề khi chạy container thủ công ở quy mô lớn.
- Nắm vững **Kubernetes** architecture và các thành phần cốt lõi.
- Biết cách bắt đầu học và thực hành Kubernetes trong môi trường local.

### Diễn giả

- **Bao Huynh** — Junior Cloud Native Developer tại Endava Vietnam, Founder/Head của ITea Lab
  - Swinburne alumni
  - Cựu Cloud DevOps Engineer tại NAB Innovation Centre Vietnam

### Nội dung nổi bật

- **Container Orchestration**: tự động hóa deploy, scaling, self-healing trên cluster.
- **Kubernetes Architecture**: Control Plane (etcd, api-server, scheduler) + Worker Nodes.
- **Core objects**: Pod, ReplicaSet, Deployment, ConfigMap, Secret, Jobs, Services.
- **Manifest YAML + kubectl basics**: cách viết và áp dụng cấu hình.
- **EKS** (Amazon Elastic Kubernetes Service): chạy Kubernetes trên AWS với tích hợp tốt AWS services.
- **Helm Charts & K9s**: package manager và terminal UI cho Kubernetes.

### Bài học rút ra

- **Design Mindset**: declarative configuration cho hạ tầng.
- **Technical Architecture**: cluster, node, pod hierarchy cho thiết kế ứng dụng scalable.
- **Modernization Strategy**: từ Docker Compose → Kubernetes cho production workloads.
- **Standardized deployment patterns**: blue-green, canary, rolling updates.

### Ứng dụng

- Dùng **Minikube/K3D** để thực hành Kubernetes trên laptop cá nhân.
- Viết **Deployment + Service manifest** cho project hiện tại.
- Sử dụng **Helm** để chuẩn hóa deployment qua các môi trường dev/staging/prod.

### Trải nghiệm

- Live demo **Kubernetes cluster** sử dụng Minikube/K3D.
- Hands-on **kubectl commands** trong tình huống thực tế.
- Thảo luận networking: EKS vs self-hosted Kubernetes.

---

## 3. Infrastructure as Code with Terraform on AWS

### Mục tiêu sự kiện

- Hiểu tại sao **ClickOps** không phù hợp với production environment.
- So sánh các **IaC tool**: CloudFormation, CDK, Terraform.
- Nắm cách **Terraform** hoạt động và workflow cơ bản trên AWS.

### Diễn giả

- **Thinh Nguyễn** (Khanh Phuc Thinh Nguyen) — FCAJ Cloud Engineer Trainee, ITea Lab Operations Team
  - Sinh viên năm 3 Swinburne, chuyên ngành Computer Science
  - FCAJ member 2025
  - Operations Team contributor tại ITea Lab

### Nội dung nổi bật

- **ClickOps vs IaC**: click console chậm, dễ lỗi, khó cộng tác → **IaC** giải quyết bằng automation & reproducibility.
- **AWS CloudFormation**: YAML/JSON template, Stack management, Drift Detection.
- **AWS CDK**: IaC bằng ngôn ngữ lập trình thực (Python, TypeScript), 3 cấp Constructs (L1/L2/L3).
- **Terraform**: multi-cloud (AWS/Azure/GCP), HCL syntax, state tracking với tfstate.
- **Terraform workflow**: init → validate → plan → apply → destroy.

### Bài học rút ra

- **Design Mindset**: "infrastructure = code" — version-controlled, reviewable, reproducible.
- **Technical Architecture**: provider → resource → state model.
- **Modernization Strategy**: migrate ClickOps → IaC từng bước.
- **Infrastructure reproducibility**: dễ nhân bản môi trường dev/staging/prod.

### Ứng dụng

- Viết **Terraform script** để provision môi trường dev thay vì click console.
- Dùng **CDK L2/L3 Constructs** để deploy AWS resources với best practices built-in.
- Bật **Drift Detection** trong CloudFormation để phát hiện thay đổi ngoài IaC.
- Version-control tất cả infrastructure code để dễ audit trail và rollback.

### Trải nghiệm

- Live demo tạo **S3 bucket** với **3-level CDK Constructs**.
- Hands-on **Terraform commands** trực tiếp.
- So sánh thực tế: **CloudFormation vs CDK vs Terraform**.
- Thảo luận về alternatives: **OpenTofu**, **Pulumi** và các IaC tools khác.

---

## Bài học chung từ sự kiện

- **Modern DevOps Architecture**: từ monolithic VM → container → orchestrated Kubernetes → serverless alternatives, tối ưu cost và operational burden.
- **Event-Driven Systems**: giảm coupling và tăng throughput nhờ message queue / event bus.
- **Cloud-Native Design Mindset**: stateless design, horizontal scaling, resilience, observable ngay từ đầu.
- **Cost Optimization**: case study thực tế — Elixir giảm $30K/tháng xuống $397/tháng.
- **Amazon Q Developer**: AI assistant hỗ trợ viết code, tạo cloud resources, gợi ý architecture.
- Áp dụng IaC (Terraform/CDK) để nhất quán & auditability cho toàn bộ hạ tầng.
