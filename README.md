# Telcolearn-Terraform
Daily log of Terraform setup and installation issues — includes errors, fixes, and configuration notes

## 🧩 Overview
This repository documents my daily setup issues, solutions, and learnings while installing and configuring **Terraform** on an **AWS EC2 instance** (used as a virtual machine) and connecting through **MobaXterm**

## ⚙️ Environment Details
- **Instance Type:** AWS EC2 (Ubuntu)
- **Connection Tool:** MobaXterm
- **Purpose:** Practice Terraform setup, configuration, and resource provisioning

## 🪜 Installation Steps
### 1. Connected to EC2 instance
- Launched an Ubuntu EC2 instance from AWS Console  
- Downloaded the `.pem` key file  
- Connected to EC2 using **MobaXterm**:
  ssh -i "key.pem" ubuntu@<EC2-public-IP>

**2. Updated the system**
sudo apt-get update -y
sudo apt-get upgrade -y

**3. Installed Terraform**
sudo apt-get install wget unzip -y
wget https://releases.hashicorp.com/terraform/1.9.7/terraform_1.9.7_linux_amd64.zip
unzip terraform_1.9.7_linux_amd64.zip
sudo mv terraform /usr/local/bin/
terraform -version

**⚠️ Issues Faced During Setup**
terraform: command not found	Added Terraform binary to /usr/local/bin and rechecked PATH
Permission denied while moving binary	Used sudo with the mv command
Network timeout while downloading Terraform	Checked EC2 security group outbound rules and retried

✅ Verification
To verify installation:

terraform -version

Output:
nginx
Terraform v1.9.7
on linux_amd64

## ✅ Summary
This README will be updated daily with installation challenges and resolutions for learning and reference.
