# Single Configurable Web Server

This Terraform configuration deploys a single, configurable web server in AWS. The infrastructure includes a VPC with a public subnet and an EC2 instance running Apache web server.

## Features

- Configurable VPC with a public subnet
- Single EC2 instance with Apache web server
- Security group with HTTP/HTTPS access
- Amazon Linux 2 based web server
- Configurable instance type

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
- `vpc_cidr`: CIDR block for VPC (default: 10.0.0.0/16)
- `public_subnet_cidr`: CIDR block for public subnet (default: 10.0.1.0/24)

## Outputs

After successful deployment, you can access these outputs:

- `instance_public_ip`: Public IP address of the web server
- `instance_public_dns`: Public DNS name of the web server
- `vpc_id`: ID of the created VPC
- `public_subnet_id`: ID of the public subnet
- `web_security_group_id`: ID of the web server security group

## Clean Up

To destroy the infrastructure:
```bash
terraform destroy
```

## Architecture

The infrastructure consists of:
1. VPC with a public subnet
2. Internet Gateway for public internet access
3. Single EC2 instance running Apache
4. Security Group for controlling access