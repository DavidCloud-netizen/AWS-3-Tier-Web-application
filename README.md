# AWS-3-Tier-Web-application
AWS 3 tier web application architecture project 
# 3-Tier Web Application Architecture with AWS

## Objective:
The goal of this project is to design and deploy a highly scalable and secure 3-tier web application architecture on AWS. The architecture consists of a presentation layer (Web Tier), an application layer (App Tier), and a data layer (Database Tier), leveraging AWS services like EC2, RDS, ELB, and Auto Scaling to ensure optimal performance, scalability, and reliability.

## VPC and Subnets:
- A Virtual Private Cloud (VPC) is created to isolate and securely manage resources.
- Three subnets are configured: one for the web tier, one for the application tier, and one for the database tier.
- Each subnet is placed in different Availability Zones (AZs) for fault tolerance and high availability.
- Network Access Control Lists (NACLs) and Security Groups are applied for proper access control.

## Amazon Machine Image (AMI) and Launch Template:
- Custom AMIs are created for the web and application servers to ensure a consistent deployment.
- A launch template is used to automate the deployment of EC2 instances with pre-defined configurations, such as instance type, AMI, and key pairs.
- The launch template is integrated with the Auto Scaling group to ensure flexibility and scalability.

## Auto Scaling Group:
- An Auto Scaling Group (ASG) is configured for the web and application tiers to automatically scale EC2 instances based on demand.
- The scaling policies are set up to monitor CPU utilization and increase or decrease the number of instances as needed.
- This ensures that the application can handle traffic fluctuations efficiently without manual intervention.

## Elastic Load Balancer (ELB):
- An Elastic Load Balancer (ELB) is used to distribute incoming traffic evenly across the EC2 instances in the web tier.
- The ELB automatically adjusts its capacity to handle the traffic volume, providing high availability and fault tolerance.
- SSL termination is configured to ensure secure communication between clients and the application.

## Bastion Server:
- A Bastion Host is used to securely access instances within the private subnets (e.g., database instances) from the internet.
- Access is restricted using SSH keys, and proper security group rules are set to limit connections.

## MySQL RDS:
- A MySQL RDS instance is deployed in the database tier to handle all database-related operations.
- The RDS instance is configured for high availability with Multi-AZ deployment to provide automatic failover and minimize downtime.
- Automated backups, patch management, and database monitoring are enabled for optimal performance and reliability.

## Simple Notification Service (SNS) Notifications:
- SNS is used to send notifications for important events, such as EC2 instance scaling actions, RDS backups, or system failures.
- SNS topics are set up to allow multiple recipients to subscribe and receive updates in real-time.
- This provides timely alerts to stakeholders for better management and troubleshooting.

## Key Achievements:
- Successfully implemented a fault-tolerant, scalable, and secure 3-tier web application architecture on AWS.
- Automated deployment of web and application tiers using AMIs, Launch Templates, and Auto Scaling.
- Configured an Elastic Load Balancer to distribute traffic efficiently across multiple EC2 instances.
- Deployed a MySQL RDS instance with high availability and automated backups to ensure data integrity.
- Enabled real-time notifications using SNS to stay updated on critical events.

## Challenges:
- Ensuring high availability and fault tolerance across multiple AWS services while managing complex network configurations.
- Properly securing and configuring network access control, ensuring the system is protected against unauthorized access.
- Optimizing the Auto Scaling policies to balance cost efficiency with performance during peak loads.
- Managing database backups and ensuring minimal downtime during RDS instance maintenance or failover events.

## Service Usage:
- **Amazon EC2**: Used for hosting web and application servers, providing scalable compute capacity.
- **Amazon RDS (MySQL)**: Managed relational database for storing application data with high availability.
- **Elastic Load Balancer (ELB)**: Distributes incoming traffic to EC2 instances to ensure high availability and performance.
- **Auto Scaling**: Automatically adjusts the number of EC2 instances based on traffic demands to ensure optimal resource usage.
- **Amazon VPC**: Used to isolate resources, with subnets across different availability zones for fault tolerance.
- **Amazon SNS**: Sends real-time notifications about important system events, ensuring timely updates for system management.
- **AWS IAM**: Manages access control and permissions for securely interacting with AWS resources.

