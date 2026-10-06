## Architecture

```text
                         Terraform
                             |
                             v
                     +---------------+
                     |      AWS      |
                     +---------------+
                             |
              +--------------+--------------+
              |                             |
              v                             v
           VPC                         S3 Bucket
       10.0.0.0/16
              |
              v
       +-------------+
       | Public      |
       | Subnet      |
       | 10.0.1.0/24|
       +-------------+
              |
       +------+------+
       |             |
       v             v
 Internet       Route Table
 Gateway             |
                     v
              Internet Gateway
                     |
                     v
              Security Group
                     |
                     v
                  EC2
                     |
                     v
                  Nginx
                     |
                     v
              Web Browser

------------------------------------------------------------------------------------------------------------------------------------
# AWS Infrastructure Provisioning with Terraform

This project demonstrates how to provision and manage AWS infrastructure using **Terraform Infrastructure as Code (IaC)**.

Instead of manually creating AWS resources through the AWS Management Console, Terraform is used to define, create, modify, and destroy the infrastructure.

---

##  Project Overview

The project creates a small AWS infrastructure consisting of:

- Amazon VPC
- Public Subnet
- Internet Gateway
- Route Table
- Route Table Association
- Security Group
- EC2 Instance
- Nginx Web Server
- Amazon S3 Bucket

The EC2 instance is deployed inside the VPC public subnet and configured to run an Nginx web server.
