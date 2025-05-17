# 🛒 Cloud-Based E-Commerce Website on AWS

This project is a scalable, secure, and globally accessible cloud-based e-commerce web application hosted on Amazon Web Services (AWS). The project was built for practical learning purposes and demonstrates real-world deployment strategies using multiple AWS services.

---

## 📌 Project Objectives
![image](https://github.com/user-attachments/assets/e8dc081c-3533-401c-92ec-4ff4e32f48e9)

---
Architecture Diagram.
![image](https://github.com/user-attachments/assets/fb682d1a-84b2-4014-9857-cb53fcf52d7b)


## 🧰 AWS Services Used

| Service          | Purpose |
|------------------|---------|
| EC2              | Hosting the web server with Flask/Django |
| RDS (PostgreSQL) | Managed backend database for storing product and order data |
| Route 53         | Custom domain management and global DNS routing |
| S3               | Static content storage (product images, CSS/JS) |
| CloudFront       | Global CDN for faster asset delivery |
| Elastic Load Balancer | Ensures fault-tolerance across multiple EC2 instances |
| IAM              | Role-based access control |
| Certificate Manager (ACM) | Provisioning SSL certificates |
| Lambda           | Inventory auto-update on new order event |
| SQS/SNS          | Event-driven architecture for order processing |
| VPC/Subnets      | Secure network segmentation and isolation |

---

## 🛠️ Steps Followed

1. **Domain & DNS Setup**
   - Purchased domain `e-comer.store` via IONOS
   - Switched DNS authority to **AWS Route 53**
   - Configured `A` and `CNAME` records for root and `www`

2. **EC2 Setup**
   - Launched Ubuntu EC2 instance in public subnet
   - Installed and configured web server (Gunicorn + Nginx)
   - Deployed Flask app using Git + pip + virtualenv

3. **Database Setup**
   - Created a Aurora PostgreSQL database on Amazon RDS (Encrypted, Multi-AZ)
   - Connected EC2 app to RDS using credentials securely stored in environment variables

4. **Global Access & Performance**
   - Configured **Route 53** for domain routing
   - Added **CloudFront** for CDN acceleration
   - Set up **SSL via AWS Certificate Manager**

5. **Real-Time Inventory System**
   - Order events pushed to **SQS queue**
   - **Lambda** function updates inventory count in real-time
   - Alerts optionally sent via **SNS**

Future deployments considered ![image](https://github.com/user-attachments/assets/2a2f701c-71c6-4475-bb9c-14dd063f80e8)

