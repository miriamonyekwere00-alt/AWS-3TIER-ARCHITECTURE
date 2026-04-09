# AWS 3-Tier Production Architecture
**Built by:** Miriam | Fribourg, Switzerland | 2026

## Project Overview
A fully functional production grade AWS architecture 
built from scratch using the AWS Console.

## Architecture Diagram
Internet → ALB → ASG → EC2 (Private) → RDS MySQL (Private)
                                    ↓
                               S3 Bucket (via IAM Role)

## What I Built
- Custom VPC with CIDR 10.0.0.0/16
- 4 Subnets across 2 Availability Zones
- Internet Gateway & NAT Gateway
- Application Load Balancer (internet facing)
- Auto Scaling Group with Launch Template & User Data
- EC2 instances in private subnets
- RDS MySQL database in private subnets
- S3 bucket integrated securely via IAM Role
- Bastion Host for secure private access
- Security Groups following least privilege

## Key Concepts Demonstrated
- High availability across multiple AZs
- Self healing infrastructure
- Secure private subnet architecture
- IAM best practices (no access keys)
- Cost efficient auto scaling

## Screenshots
See uploaded screenshots for full evidence.
