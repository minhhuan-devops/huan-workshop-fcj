---
title : "Prerequiste"
date : 2024-01-01 
weight : 2 
chapter : false
pre : " <b> 4.2. </b> "
---

### 1. Install AWS CLI

The AWS Command Line Interface (AWS CLI) is a unified tool to manage your AWS services.

#### Windows
Download and run the MSI installer:
[Download AWS CLI for Windows](https://awscli.amazonaws.com/AWSCLIV2.msi)

#### macOS
Using Homebrew:
```bash
brew install awscli
```
Or download the standard installer:
```bash
curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
sudo installer -pkg AWSCLIV2.pkg -target /
```

#### Linux
Install via command line:
```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

Verify the installation:
```bash
aws --version
```

### 2. Configure AWS CLI

After installing, you need to configure credentials so Terraform can interact with AWS. Run the following command:
```bash
aws configure
```
Enter your `AWS Access Key ID`, `AWS Secret Access Key`, `Default region name` (e.g., `us-east-1` or `ap-southeast-1`), and `Default output format` (enter `json`).

### 3. Install Terraform

Terraform is an Infrastructure as Code (IaC) tool for building, changing, and managing infrastructure safely and efficiently.

#### Windows
Using Chocolatey:
```bash
choco install terraform
```
Or download the zip file directly from the [Terraform downloads page](https://developer.hashicorp.com/terraform/downloads) and add the executable path to your Environment Variables.

#### macOS
Using Homebrew:
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

Verify the installation:
```bash
terraform --version
```

### 4. Git and Code Editor
- **Git:** Used to clone the workshop source code.
- **Visual Studio Code (VS Code):** Recommended code editor. Install the `HashiCorp Terraform` extension for better syntax highlighting and support.

### 5. Deploy the architecture with Terraform

After all tools are installed, clone the repository and run the following commands to provision the entire architecture:

```bash
git clone https://github.com/huan-workshop-fcj.git # (replace with actual repo link if needed)
cd huan-workshop-fcj/terraform
terraform init
terraform plan
terraform apply --auto-approve
```

This process might take 15 - 20 minutes to initialize RDS, ElastiCache, ALB, and Fargate containers.