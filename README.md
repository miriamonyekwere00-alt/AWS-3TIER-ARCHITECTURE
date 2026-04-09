# AWS 3-Tier Architecture Project

## Overview
Production grade AWS infrastructure built from scratch.

## Architecture
- VPC with public and private subnets across 2 Availability Zones
- Application Load Balancer for traffic distribution
- Auto Scaling Group for self healing infrastructure
- EC2 instances in private subnets
- RDS MySQL database in private subnets
- S3 bucket integrated via IAM Role
- NAT Gateway for private subnet internet access
- Bastion Host for secure server access

## Technologies Used
- AWS VPC, Subnets, IGW, NAT Gateway
- EC2, ALB, ASG, Launch Template
- RDS MySQL
- S3
- IAM Roles and Policies
- AWS Security Groups

## Screenshots
See screenshots folder for full architecture evidence.

## Author
Built by Miriam | Fribourg, Switzerland | 2026
