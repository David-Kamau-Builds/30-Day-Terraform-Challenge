# Day 3: AWS Infrastructure with Terraform

This directory contains two Terraform projects that demonstrate different AWS infrastructure deployment patterns:

## 📂 Projects

### 1. Single Server Application
A basic infrastructure setup with a single EC2 instance in a public subnet.

**Key Components:**
- VPC with public subnet
- Internet Gateway and Route Table
- Security Group for SSH and HTTP
- Single EC2 instance with Apache web server

[View Single Server Application →](./single-server-application/)

### 2. Web Server Application with Auto Scaling
A more advanced setup with high availability and auto scaling capabilities.

**Key Components:**
- VPC with multiple public subnets across AZs
- Application Load Balancer
- Auto Scaling Group
- Launch Template with user data
- Security Groups for ALB and instances
- CloudWatch alarms for scaling
- Enhanced security features (HTTPS, IAM roles, logging)

[View Web Server Application →](./web-server-application/)

## 🔐 Security Improvements

Both projects include security best practices:
- Restricted SSH access to specific IP addresses
- HTTPS support for encrypted traffic
- IAM roles for EC2 instances (principle of least privilege)
- Proper logging configuration
- Provider version constraints

## 🚀 Getting Started

Each project directory contains its own README with detailed instructions on:
- Prerequisites
- Deployment steps
- Access instructions
- Cleanup procedures

## 📋 Requirements

- Terraform v0.14+
- AWS CLI configured with appropriate credentials
- EC2 key pair for SSH access