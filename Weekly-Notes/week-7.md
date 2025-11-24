## Week 7 Notes

## AWS Well-Architected Framework

A guideline set for building secure, high-performing, resilient, and efficient cloud systems. It helps review architectures and identify improvements. It is organized into six pillars: Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimization, and Sustainability. The goal is to build workloads that are scalable, cost-effective, and fault-tolerant.

##  Well-Architected Principles

(per pillar) Operational Excellence Automate everything, including deployments, monitoring, and rollbacks. Use version control and make small, reversible changes. Prioritize observability. Security Use least privilege access. Enable multi-factor authentication, encryption, and logging. Automate security checks and alerts. Reliability Design for failure. Use multi-AZ, automatic scaling, and backups. Test recovery often. Performance Efficiency Choose the right compute and storage options. Use managed services when possible. Scale horizontally. Cost Optimization Pay only for what you use. Use cost monitoring and budgets. Right-size resources and take advantage of reserved or savings plans. Sustainability Use energy-efficient instance types. Optimize workloads to reduce compute waste. Prefer serverless when possible.
 
## AWS CLI

This is a command-line tool for interacting with AWS services. It is useful for automation, scripting, and CI/CD pipelines. Common commands include: aws configure → set credentials aws s3 ls → list S3 buckets aws ec2 describe-instances → view EC2 details It works with IAM permissions in the background.

## AWS IAM

 (Identity and Access Management) This controls who can access what in AWS. IAM Components: Users → individual accounts Groups → collections of users Roles → temporary permissions for services or users Policies → JSON documents that define allowed actions Best practices include: Least privilege Multi-factor authentication for all users Avoid using root accounts Rotate access keys
 
## Operations on AWS

This focuses on monitoring, automation, and maintaining workloads. Common tools and services include: CloudWatch → logs, metrics, alarms CloudTrail → API activity tracking AWS Config → resource compliance Systems Manager → patching, automation, inventory Key operational tasks are: Deploy updates safely. Monitor performance and costs. Secure and back up resources. Test disaster recovery plans.



