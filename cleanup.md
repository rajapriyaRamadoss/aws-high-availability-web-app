# AWS Project Cleanup Guide

## Purpose
This guide lists the AWS resources to review and delete after completing the project to help avoid ongoing charges.

## Resources to Review
- EC2 instances
- Auto Scaling Group
- Application Load Balancer
- Target Group
- Launch Template
- Custom AMI and associated EBS snapshots
- CloudWatch alarm
- SNS topic and email subscription
- Security group
- Internet Gateway
- Route table
- Public subnets
- Custom VPC

## Cleanup Order
1. Set the Auto Scaling Group desired capacity to 0, then delete the Auto Scaling Group.
2. Delete the Application Load Balancer.
3. Delete the Target Group after it is no longer in use.
4. Delete the Launch Template if it is no longer needed.
5. Terminate any remaining EC2 instances.
6. Deregister the custom AMI and delete its associated snapshots if they are no longer needed.
7. Delete the CloudWatch alarm and SNS topic if they are no longer needed.
8. Delete the custom security group.
9. Detach and delete the Internet Gateway.
10. Delete the route table associations and custom route table.
11. Delete the subnets.
12. Delete the custom VPC.

## Important Notes
- Check the AWS console for dependencies before deleting resources.
- Review the AWS Billing dashboard after cleanup.
- Keep the IAM user only if it is still needed; otherwise, remove it according to your security requirements.
- Deleting resources may be irreversible.

