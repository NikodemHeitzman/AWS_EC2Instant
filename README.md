# AWS_EC2Instant
Deployment of a secure, public-facing web server on AWS EC2. Includes Linux administration, Security Group configuration (PoLP), and automated web server setup.

# 🌐 AWS Cloud Infrastructure: Web Server Deployment

[![AWS](https://img.shields.io/badge/AWS-Amazon%20EC2-FF9900?logo=amazonec2&logoColor=white)](https://aws.amazon.com/ec2/)
[![Linux](https://img.shields.io/badge/Linux-Ubuntu%20%2F%20Amazon%20Linux-FCC624?logo=linux&logoColor=black)](https://www.linux.org/)

## 📝 Project Overview
This project demonstrates the end-to-end process of deploying a publicly accessible web server on **Amazon Web Services (AWS)**. It focuses on setting up virtual infrastructure, managing security policies, and configuring a Linux environment for web hosting.



## 🎯 Objectives
* **Infrastructure as a Service (IaaS):** Provisioning a Linux-based EC2 instance.
* **Network Security:** Implementing the Principle of Least Privilege via Security Groups.
* **Server Administration:** Remote management via SSH and web server configuration.
* **Web Hosting:** Serving live content over the HTTP protocol.

## 🛠 Tech Stack & Services
* **Cloud Provider:** AWS (Amazon Web Services)
* **Compute:** EC2 (Elastic Compute Cloud)
* **OS:** Linux (Amazon Linux 2)
* **Web Server:** Nginx
* **Networking:** VPC, Public Subnets, Security Groups

## 🚀 Implementation Steps

### 1. Instance Provisioning & Networking
* Launched an **EC2 Instance** (t2.micro) within a public subnet.
* Configured a **Security Group** with granular inbound rules:
    * **HTTP (80):** Allowed from `0.0.0.0/0` for global access.
    * **SSH (22):** Restricted to my specific IP address for secure management.

### 2. Server Configuration
Connected to the instance via SSH and executed the following environment setup:
```bash
# Update system and install Apache
sudo yum update -y
sudo yum install -y httpd
sudo systemctl start httpd
sudo systemctl enable httpd
