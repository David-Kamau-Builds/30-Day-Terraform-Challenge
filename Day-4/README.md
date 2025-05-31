# AWS Web Server Infrastructure Configurations

This repository contains two Terraform configurations for deploying web servers in AWS:

1. **Single Web Server** (`/single_webserver`): Deploy a single, configurable web server with basic networking infrastructure.
2. **Web Server Cluster** (`/web_cluster`): Deploy a highly available, scalable web server cluster with auto-scaling and load balancing.

## Repository Structure

```
.
├── single_webserver/     # Single web server configuration
│   ├── main.tf          # Main infrastructure configuration
│   ├── variables.tf     # Input variables
│   ├── outputs.tf       # Output values
│   ├── providers.tf     # Provider configuration
│   └── README.md        # Documentation
│
├── web_cluster/         # Web server cluster configuration
│   ├── main.tf          # Base infrastructure configuration
│   ├── web_cluster.tf   # Cluster-specific resources
│   ├── variables.tf     # Input variables
│   ├── outputs.tf       # Output values
│   ├── providers.tf     # Provider configuration
│   └── README.md        # Documentation
│
└── README.md            # This file
```

## Prerequisites

- Terraform >= 1.0.0
- AWS CLI configured with appropriate credentials
- AWS account with necessary permissions

## Usage

Choose the appropriate configuration based on your needs:

### Single Web Server

For a basic web server setup, use the configuration in the `single_webserver` directory:

```bash
cd single_webserver
terraform init
terraform plan
terraform apply
```

### Web Server Cluster

For a scalable, highly available setup, use the configuration in the `web_cluster` directory:

```bash
cd web_cluster
terraform init
terraform plan
terraform apply
```

## Documentation

Each configuration directory contains its own README.md with detailed information about:
- Features and capabilities
- Configuration options
- Available outputs
- Architecture details
- Clean-up instructions

## Clean Up

To destroy the infrastructure, navigate to the appropriate directory and run:
```bash
terraform destroy
```