#   AWS 3-Tier Production Architecture  
**Built by:** Miriam | Fribourg, Switzerland | 2026  

---

##   Project Overview  
This project demonstrates a production-style 3-tier architecture built on AWS with a focus on **high availability, security, and scalability**.

The system is designed to handle real-world application traffic while maintaining isolation between public and private resources.

---

##    Architecture Flow  

User → Application Load Balancer → EC2 (Private Subnets) → RDS MySQL  
                                      ↓  
                                   S3 (via IAM Role)  

###   Admin Access:  
Admin → Bastion Host → Private EC2  

---

##   Infrastructure Components  

- Custom VPC (`10.0.0.0/16`)  
- 2 Public Subnets (for ALB & Bastion)  
- 2 Private Subnets (for EC2 & RDS)  
- Internet Gateway (public access)  
- NAT Gateway (private outbound access)  
- Application Load Balancer (internet-facing)  
- Auto Scaling Group with Launch Template & User Data  
- EC2 instances in private subnets  
- RDS MySQL database in private subnets  
- S3 bucket integrated securely via IAM Role  
- Bastion Host for secure SSH access  
- Security Groups configured with least privilege  

---

##  Security Design  

- ALB allows HTTP access from `0.0.0.0/0`  
- EC2 only allows HTTP from ALB Security Group  
- RDS only allows MySQL access from EC2 Security Group  
- No public access to EC2 or RDS  
- IAM Role used for S3 access (no access keys stored)  

---

##   Key Features  

- High availability across multiple Availability Zones  
- Auto Scaling for dynamic traffic handling  
- Self-healing infrastructure  
- Secure private subnet architecture  
- Cost-aware design using minimal always-on resources  

---

##  Challenges & Lessons Learned  

During the build, several real-world issues were encountered and resolved:

- Load Balancer showing **unhealthy targets**  
  → Traced to instance configuration issues and resolved by rebuilding EC2 correctly  

- Confusion with Security Groups  
  → Learned importance of separating ALB and EC2 security boundaries  

- Apache installation failure  
  → Discovered OS differences (`apt` vs `yum`)  

- S3 integration misunderstanding  
  → Learned that EC2 must explicitly fetch and serve S3 content  

- Debugging connectivity issues  
  → Practiced systematic troubleshooting (Security Groups → NACL → Routing → Instance)  

---

##  Key Concepts Demonstrated  

- Multi-AZ architecture design  
- Network isolation (public vs private subnets)  
- Load balancing and traffic routing  
- IAM role-based access control  
- Infrastructure troubleshooting and debugging  

---

##  Future Improvements  

- Replace Bastion Host with AWS Systems Manager (SSM)  
- Add HTTPS with ACM (SSL/TLS)  
- Integrate CloudFront for global content delivery  
- Implement CI/CD pipeline (CodePipeline or GitHub Actions)  

---

## Screenshots  

See uploaded screenshots for full implementation details.
