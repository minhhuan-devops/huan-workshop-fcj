---
title: "Event 4"
date: 2026-04-04
weight: 4
chapter: false
pre: " <b> 3.4. </b> "
---

## 1. Elixir as a Unified Solution for Highly Concurrent & Fault-Tolerant DevOps Infrastructure

### Event Objectives

- Introduction to **Elixir** and **functional programming** on **BEAM VM**.
- Understanding how **Elixir** achieves high **fault-tolerance** through **OTP** and **process supervision**.
- Applying **Elixir** to **DevOps pipelines** as a unified toolset.

### Speaker

- **Nguyen Ta Minh Triet** — R&D Member at ITea Lab, SAP Developer Intern at Bosch GSV
  - Swinburne 3rd-year Computer Science/Software Development student
  - Published 2 conference papers on Elixir (CCIOT 2025, SCI 2026)
  - FCJ member and ITea Lab contributor

### Key Highlights

- **BEAM VM** — same foundation as Erlang with Ruby-like syntax.
- **BEAM Process**: lightweight processes with no shared memory, supporting millions of concurrent processes.
- **"Let It Crash" philosophy** — supervisors automatically restart failed processes instead of try/catch.
- **Hot Code Upgrades** — upgrade systems without downtime.
- **Unified toolset** — one language for testing, deployment, and monitoring.
- **Real-world case study**: migration from AWS Lambda to Elixir reduced costs from **$30K/month → $397/month**.

### Key Takeaways

- **Design Mindset**: functional & immutable architecture.
- **Technical Architecture**: process-based concurrency with robust supervision trees.
- **Modernization Strategy**: replacing serverless with BEAM for cost optimization and fault tolerance.
- Demonstrated with **2M+ WebSocket connections** on a single server.

### Applying to Work

- Apply the **"Let It Crash"** philosophy to simplify error handling in distributed systems.
- Consider **BEAM/Elixir** for services requiring high concurrency (IoT, WebSocket, real-time streaming).
- Optimize cloud costs by migrating from serverless to **Elixir** for suitable workloads.

### Event Experience

- Live demo of **Elixir IoT Edge Server** running in Docker.
- Hands-on experience with **concurrent processing** and **OTP supervision trees**.
- Real-world performance: **2M WebSocket connections** on a single server.

---

## 2. Architecting for the Cloud with Kubernetes

### Event Objectives

- Understand the challenges of running containers manually at scale.
- Master **Kubernetes** architecture and core components.
- Learn how to start with Kubernetes in local environments.

### Speaker

- **Bao Huynh** — Junior Cloud Native Developer at Endava Vietnam, Founder of ITea Lab
  - Swinburne alumni
  - Former Cloud DevOps Engineer at NAB Innovation Centre Vietnam

### Key Highlights

- **Container Orchestration**: automate deployment, scaling, and self-healing across clusters.
- **Kubernetes Architecture**: Control Plane (etcd, api-server, scheduler) + Worker Nodes.
- **Core objects**: Pod, ReplicaSet, Deployment, ConfigMap, Secret, Jobs, Services.
- **Manifest YAML + kubectl basics**: writing and applying configurations.
- **EKS** (Amazon Elastic Kubernetes Service): Kubernetes on AWS with minimal setup and tight AWS integration.
- **Helm Charts & K9s**: package manager and terminal UI for Kubernetes management.

### Key Takeaways

- **Design Mindset**: declarative infrastructure configuration.
- **Technical Architecture**: cluster, node, pod hierarchy for scalable application design.
- **Modernization Strategy**: transitioning from Docker Compose → Kubernetes for production.
- **Standardized deployment patterns**: blue-green, canary, and rolling updates.

### Applying to Work

- Use **Minikube/K3D** to practice Kubernetes locally.
- Write **Deployment + Service manifests** for current projects.
- Use **Helm** to standardize deployments across dev/staging/prod environments.

### Event Experience

- Live demo of a **Kubernetes cluster** using Minikube/K3D.
- Hands-on **kubectl commands** for real-world scenarios.
- Discussion comparing EKS vs self-hosted Kubernetes.
- Recommended resources: **LFS158**, **kubernetes.io**, **Kelsey Hightower** tutorials.

---

## 3. Infrastructure as Code with Terraform on AWS

### Event Objectives

- Understand why **ClickOps** is unsuitable for production environments.
- Compare **IaC tools**: CloudFormation, CDK, Terraform.
- Master **Terraform** workflow and core concepts on AWS.

### Speaker

- **Thinh Nguyễn** (Khanh Phuc Thinh Nguyen) — FCAJ Cloud Engineer Trainee, ITea Lab Operations Team
  - Swinburne 3rd-year Computer Science student
  - FCAJ member 2025
  - Operations Team contributor at ITea Lab

### Key Highlights

- **ClickOps vs IaC**: manual console operations are slow, error-prone, and hard to collaborate on → **IaC** solves this with automation & reproducibility.
- **AWS CloudFormation**: YAML/JSON templates, Stack management, Drift Detection.
- **AWS CDK**: Infrastructure as code in real programming languages (Python, TypeScript), with 3 Construct levels (L1/L2/L3).
- **Terraform**: multi-cloud (AWS/Azure/GCP), HCL syntax, state management with tfstate.
- **Terraform workflow**: init → validate → plan → apply → destroy.

### Key Takeaways

- **Design Mindset**: "infrastructure = code" — version-controlled, reviewable, reproducible.
- **Technical Architecture**: provider → resource → state model.
- **Modernization Strategy**: gradual migration from ClickOps → IaC.
- **Infrastructure reproducibility**: easily clone environments for dev/staging/prod consistency.

### Applying to Work

- Write **Terraform scripts** to provision dev environments instead of clicking the console.
- Use **CDK L2/L3 Constructs** to deploy AWS resources with built-in best practices.
- Enable **Drift Detection** in CloudFormation to detect untracked infrastructure changes.
- Version-control all infrastructure code for audit trails and easy rollback.

### Event Experience

- Live demo creating **S3 buckets** with **3-level CDK Constructs**.
- Hands-on **Terraform commands** demonstration.
- Direct comparison: **CloudFormation vs CDK vs Terraform** in real scenarios.
- Discussion of alternatives: **OpenTofu**, **Pulumi**, and other IaC tools.

---

## Overall Event Takeaways

- **Modern DevOps Architecture**: from monolithic VMs → containers → orchestrated Kubernetes → serverless alternatives; optimizing cost and operational overhead.
- **Event-Driven Systems**: reduce coupling and enable high throughput through message queues and event buses.
- **Cloud-Native Design Mindset**: stateless design, horizontal scaling, resilience, and observability from day one.
- **Cost Optimization**: Elixir reduced $30K/month to $397/month in a real production case.
- **Amazon Q Developer**: AI assistant for code generation, cloud resource creation, and architecture advice.
- Standardize infrastructure with IaC (Terraform/CDK) for consistency and auditability across all environments.
