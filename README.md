# AWS High-Availability Infrastructure Deployment with Terraform

## Project Overview
This project demonstrates the design and deployment of a **secure, highly available AWS cloud environment** using **Terraform** and **Infrastructure as Code (IaC)** principles. The infrastructure is fully automated, modular, and scalable, following industry best practices for networking, compute, and security.

---

## Architecture
- **Multi-AZ VPC Deployment**: Resources are distributed across multiple Availability Zones for **fault tolerance** and **high availability**.
- **Public and Private Subnets**:  
  - **Public Subnets** host resources with external access (e.g., bastion hosts, web servers).  
  - **Private Subnets** isolate sensitive workloads without direct internet exposure.
- **Route Tables**: Dynamic routing ensures correct traffic flow between public, private, and external networks.

---

## Networking Setup
- **Internet Gateway (IGW)**: Provides inbound and outbound connectivity for public subnet resources.
- **NAT Gateway**: Enables secure outbound internet access from private subnets.
- **Dynamic Routing**: Uses Terraform `for_each` to automatically associate subnets with appropriate route tables.

---

## Compute Resources
- **Amazon EC2 Instances** deployed in both public and private subnets.
- **Cross-Platform Testing**: Instances run **Ubuntu 20.04** and **Amazon Linux 2** for compatibility testing.
- **Automated SSH Key Management** using Terraform TLS provider.

---

## Security
- **Network Segmentation**: Private subnets isolate sensitive workloads from the internet.
- **Security Groups**: Fine-grained control of inbound and outbound traffic following the principle of least privilege.
- **High Availability**: Multi-AZ design ensures minimal downtime during zone-level failures.

---

## Automation & Scalability
- **Terraform Modules & Variables**: Infrastructure is parameterized for repeatable and scalable deployments.
- **Dynamic Resource Creation**: `for_each` loops and `cidrsubnet()` functions automate subnet, route table, and security group provisioning.
- **Infrastructure as Code (IaC)** ensures consistent, version-controlled deployments across environments.

---

## Key Outcomes
- **Improved Security**: Sensitive workloads are isolated and access is restricted.
- **High Availability**: Multi-AZ deployment and resilient networking increase uptime.
- **Operational Efficiency**: Automated, repeatable deployments reduce manual errors.
- **Scalability**: Modular design allows seamless expansion of subnets, instances, and AZ coverage.

---

## Technologies Used
- **Terraform**  
- **AWS VPC & Subnetting**  
- **Internet & NAT Gateways**  
- **Amazon EC2** (Ubuntu 20.04 & Amazon Linux 2)  
- **Security Groups & TLS Key Management**  
- **Multi-AZ Architecture & High Availability**
