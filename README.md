# 🖥️ AWS Project: Application Load Balancer with 2 EC2 Web Servers

## 📌 Project Overview
This project demonstrates how to deploy a simple web application using:
- 2 Amazon EC2 instances (web servers)
- 1 Application Load Balancer (ALB)
- Auto scaling and health check basics

## 🧰 Tools Used
- AWS EC2
- AWS Elastic Load Balancer (ALB)
- Amazon VPC (default)
- Security Groups
- User Data Script (for Apache)


## 🔧 Step-by-Step Setup

### 1. Launch 2 EC2 Instances
- AMI: Amazon Linux 2
- Instance Type: t2.micro (Free Tier)
- In the **User Data** section, add this script:
```bash
#!/bin/bash
sudo yum update -y
sudo yum install -y httpd
echo "Hello from $(hostname -f)" > /var/www/html/index.html
sudo systemctl start httpd
sudo systemctl enable httpd