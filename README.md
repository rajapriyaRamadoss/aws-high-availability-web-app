# AWS Highly Available Web Application

## Project Overview

This project demonstrates how to build a highly available web application on AWS using EC2, an Application Load Balancer, Auto Scaling, CloudWatch, and SNS.

The application runs on multiple EC2 instances across two Availability Zones. The Application Load Balancer distributes incoming HTTP traffic to registered web servers, while Auto Scaling maintains the desired number of instances and can adjust capacity based on CPU utilization.

## Architecture

**Request flow:**

User → Application Load Balancer → Target Group → EC2 Web Servers

**Monitoring flow:**

EC2 Metrics → Amazon CloudWatch Alarm → Amazon SNS Email Notification

## AWS Services Used

- **Amazon VPC:** Created an isolated network for the project.
- **Public Subnets:** Deployed resources across two Availability Zones.
- **Internet Gateway:** Enabled internet connectivity for public resources.
- **Amazon EC2:** Hosted the web application using Apache HTTP Server.
- **Amazon Machine Image (AMI):** Created a reusable image of a configured web server.
- **Application Load Balancer (ALB):** Distributed incoming HTTP traffic across registered targets.
- **Target Group:** Registered EC2 instances and configured HTTP health checks.
- **Launch Template:** Stored the configuration used to launch EC2 instances.
- **Auto Scaling Group:** Configured minimum, desired, and maximum instance capacity.
- **Amazon CloudWatch:** Monitored CPU utilization and configured an alarm.
- **Amazon SNS:** Configured email notifications for alarm events.
- **AWS IAM:** Used an IAM user to manage project resources.

## Implementation Steps

1. Created an IAM user and configured project permissions.
2. Created a VPC, two public subnets, an Internet Gateway, and route table.
3. Configured a security group for web traffic and administrative access.
4. Launched two EC2 web servers and installed Apache.
5. Created a custom AMI from a configured web server.
6. Created a target group with HTTP health checks.
7. Created an internet-facing Application Load Balancer.
8. Tested application access through the ALB DNS name.
9. Created a launch template and Auto Scaling Group.
10. Configured target tracking based on average CPU utilization.
11. Created a CloudWatch CPU utilization alarm.
12. Configured an SNS email subscription and connected it to the alarm.

## Key Learnings

- AWS networking fundamentals, including VPCs, subnets, routes, and Internet Gateways.
- Deploying and configuring web servers on EC2.
- Load balancing and target health checks.
- Launch templates and Auto Scaling configuration.
- CloudWatch monitoring and SNS notifications.
- IAM permissions and AWS resource management.

## Project Status

The application was successfully accessed through the Application Load Balancer DNS name during testing.

## Future Improvements

- Provision infrastructure using Terraform.
- Automate application deployment using CI/CD.
- Configure HTTPS using AWS Certificate Manager.
- Improve security by restricting instance HTTP access to the ALB security group.
- Add infrastructure and monitoring diagrams.

## Project Screenshots

## Project Screenshots

### 1. Screenshot 1
![Screenshot 1](screenshots/Screenshot%202026-10-11%20024959.png)

### 2. Screenshot 2
![Screenshot 2](screenshots/Screenshot%202026-10-11%20025103.png)

### 3. Screenshot 3
![Screenshot 3](screenshots/Screenshot%202026-10-11%20025154.png)

### 4. Screenshot 4
![Screenshot 4](screenshots/Screenshot%202026-10-11%20025258.png)

### 5. Screenshot 5
![Screenshot 5](screenshots/Screenshot%202026-10-11%20025440.png)
## Author

**Rajapriya R**

GitHub: [rajapriyaRamadoss](https://github.com/rajapriyaRamadoss)
