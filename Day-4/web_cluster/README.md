# Clustered Web Server Infrastructure

This Terraform configuration deploys a highly available, scalable web server infrastructure in AWS. The infrastructure includes an Auto Scaling Group (ASG) of web servers behind an Application Load Balancer (ALB) for high availability and scalability.

## Features

- Configurable VPC with public subnets across multiple availability zones
- Auto Scaling Group for dynamic scaling of web servers
- Application Load Balancer for distributing traffic
- Configurable instance type and capacity settings
- Security group with HTTP/HTTPS access
- Amazon Linux 2 based web servers with Apache

## Prerequisites

- Terraform >= 1.0.0
- AWS CLI configured with appropriate credentials
- AWS account with necessary permissions

## Usage

1. Initialize Terraform:
```bash
terraform init
```

2. Review the configuration:
```bash
terraform plan
```

3. Apply the configuration:
```bash
terraform apply
```

## Configuration

The infrastructure can be customized through variables in `variables.tf`. Key configurations include:

- `aws_region`: AWS region for deployment (default: us-west-2)
- `environment`: Environment name (default: test)
- `instance_type`: EC2 instance type (default: t3.micro)
- `min_size`: Minimum number of instances (default: 2)
- `max_size`: Maximum number of instances (default: 4)
- `desired_capacity`: Desired number of instances (default: 2)
- `vpc_cidr`: CIDR block for VPC (default: 10.0.0.0/16)
- `public_subnet_cidrs`: CIDR blocks for public subnets (default: ["10.0.1.0/24", "10.0.2.0/24"])

## Outputs

After successful deployment, you can access these outputs:

- `alb_dns_name`: DNS name of the Application Load Balancer
- `vpc_id`: ID of the created VPC
- `public_subnet_ids`: IDs of the public subnets
- `web_security_group_id`: ID of the web server security group
- `autoscaling_group_name`: Name of the Auto Scaling Group
- `launch_template_id`: ID of the Launch Template

## Clean Up

To destroy the infrastructure:
```bash
terraform destroy
```

## Architecture

The infrastructure consists of:
1. VPC with public subnets across multiple AZs
2. Internet Gateway for public internet access
3. Application Load Balancer in public subnets
4. Auto Scaling Group of web servers
5. Security Group for controlling access
6. Launch Template for consistent server configuration