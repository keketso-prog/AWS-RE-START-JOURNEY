# About This Project
You are part of a startup team launching a next-generation 3D e-commerce web application. This platform will allow users to interact with 3D models of products (e.g., furniture, gadgets, fashion items) before purchasing. Millions of users are expected globally, and the experience must be fast, highly available, secure, and cost-efficient. As a Cloud Practitioner, your role is to design the cloud architecture using AWS services to support this 3D application and meet key business and technical requirements

# 1. Design the Architecture
We used AWS services such as: ▪ Amazon S3 for 3D asset storage ▪ CloudFront for content delivery ▪ EC2 / AWS Lambda for backend compute ▪ RDS / DynamoDB for product and customer data ▪ Elastic Load Balancer (ELB) for traffic distribution ▪ Route 53 for domain management ▪ CloudWatch & Trusted Advisor for monitoring and optimization

# 2. Explain Your Choices
- Write a brief document (1–2 pages) explaining:
- Why you chose each AWS service.
- How your architecture meets each of the 5 requirements.
- Any design trade-offs or challenges
  
## Team Members
- Keketso
- kwanele
- Madimetja
- Neo
- Leah

##   3D E-Commerce Platform Architecture on AWS

## High Availability Design - AWS Cloud Practitioner Project

<img width="953" height="1095" alt="image" src="https://github.com/user-attachments/assets/f56e628f-f1d7-4147-852e-b852f74ada2d" />

# Overview and Design Principles
This architecture supports a global 3D e-commerce platform that enables users to interact with high-resolution 3D product models. The design follows the AWS Well-Architected Framework and focuses on five core pillars: high availability, scalability, performance, security, and cost efficiency. The platform eliminates single points of failure through multi-region deployments, scales automatically to handle global traffic spikes, and delivers large 3D assets with minimal latency worldwide.
# Core AWS Services and Their Functions
- Route 53 serves as our global DNS service, routing users to the nearest healthy application endpoint using latency-based routing. It continuously monitors endpoint health and provides automatic failover within 30 seconds if regional deployments become unavailable.
- Amazon CloudFront operates as our content delivery network with over 400 edge locations worldwide. It caches 3D models, textures, and static assets close to users, reducing load times from seconds to milliseconds. CloudFront integrates with S3 through Origin Access Control, ensuring secure asset delivery while minimizing origin server load and data transfer costs.
# Amazon S3
- provides durable storage for all 3D assets with eleven nines of durability. We organize assets by product category and resolution level, implementing S3 Intelligent-Tiering to automatically move infrequently accessed models to lower-cost storage classes without impacting availability.
- Application Load Balancer distributes incoming traffic across multiple backend servers at Layer 7, enabling intelligent routing based on request content. It performs health checks every 30 seconds, automatically removing unhealthy servers from rotation and handling SSL termination to reduce computational burden on application servers.
- Compute Layer uses a hybrid approach. EC2 Auto Scaling Groups handle intensive tasks like real-time 3D rendering and model customization, automatically adding or removing instances based on demand. We use a mix of on-demand instances for baseline capacity and spot instances for cost-effective handling of traffic spikes. AWS Lambda manages lightweight, event-driven tasks such as cart updates and user authentication, scaling automatically from zero to thousands of executions and charging only for actual compute time.
# Database 
- DynamoDB provides sub-10ms response times for product catalog lookups with automatic scaling and multi-availability zone replication.
- Amazon Aurora handles transactional data requiring ACID compliance, such as orders and inventory, with automatic replication across three availability zones and support for read replicas to scale read operations independently.
- Amazon CloudWatch centralizes monitoring across all services, collecting metrics, logs, and events. We configure alarms to trigger notifications when thresholds are exceeded and use CloudWatch Insights to analyze trends and troubleshoot issues. This data informs auto-scaling policies and optimization decisions.
- AWS Trusted Advisor continuously scans our environment against best practices, providing recommendations for cost optimization, security improvements, and performance enhancements that we review and implement regularly.
# Meeting Key Requirements
- High Availability is achieved through multi-region deployments where Route 53 redirects traffic if entire regions fail, multi-availability zone configurations for all critical services, database replication with automatic failover, and stateless application design that stores sessions in DynamoDB rather than on individual servers.
Scalability leverages horizontal scaling across all layers.
- Auto Scaling Groups adjust EC2 instance counts based on real-time metrics, Lambda functions scale automatically to thousands of concurrent executions, DynamoDB throughput scales based on demand, and CloudFront handles traffic increases transparently through AWS-managed infrastructure.
- Performance Optimization focuses on edge caching to serve content from locations near users, database query optimization through appropriate indexing and data modeling, connection pooling to reduce overhead, and progressive loading that displays low-resolution previews while high-resolution models load in the background.
- Security Implementation uses multiple defense layers including network isolation with private subnets for backend resources, security groups that act as virtual firewalls with least-privilege access rules, IAM roles instead of embedded credentials, encryption in transit and at rest using KMS, AWS WAF to protect against common web exploits, and CloudTrail for comprehensive audit logging.
- Cost Efficiency is maintained through serverless-first architecture that eliminates idle capacity costs, reserved capacity purchases for predictable workloads at up to 75% discounts, spot instances for fault-tolerant workloads at 70-90% savings, intelligent storage tiering, and CloudFront caching that reduces origin data transfer by approximately 90%.
# Challenges and Solutions
- Compute Trade-offs: Lambda's 15-minute execution limit makes it unsuitable for complex 3D rendering jobs. We address this by using Lambda for quick operations like thumbnail generation while deploying GPU-enabled EC2 instances for intensive rendering tasks.
- Database Selection: DynamoDB excels at simple lookups but lacks SQL's flexibility for complex queries. We use DynamoDB for the product catalog and RDS Aurora for transactional data requiring joins. For analytics requiring complex aggregations, we export data to Amazon Redshift.
- Asset Size Management: High-fidelity 3D models can exceed 500MB, creating poor experiences on mobile networks. We implement multi-resolution storage with preview, standard, and high-detail versions, progressively enhancing quality based on user interaction and network conditions. CloudFront compression reduces transmission sizes by 40-60%.
- Infrastructure Complexity: Proper VPC configuration with public and private subnets, NAT gateways, and security groups requires expertise. We use Infrastructure as Code with CloudFormation to define network architecture in version-controlled templates, ensuring consistency and enabling automated compliance checking.
# Key Insights
This project demonstrated that AWS service integration creates capabilities greater than individual components. The seamless connections between CloudFront and S3, ALB and Auto Scaling Groups, and Route 53 with multi-region deployments enable robust, production-grade architecture. We learned that comprehensive monitoring is essential for optimization and troubleshooting, security requires layered approaches rather than single solutions, and cost management demands continuous attention through regular reviews and leveraging different pricing models.
# Conclusion
This architecture successfully combines AWS managed services to create a global, highly available, and cost-effective platform for 3D e-commerce. By leveraging CloudFront for content delivery, S3 for durable storage, Auto Scaling for compute elasticity, and purpose-built databases, we have designed a system capable of serving millions of users worldwide while maintaining reasonable operational costs. The design adheres to AWS Well-Architected Framework principles and provides practical experience in balancing technical requirements, business objectives, and operational constraints. This foundation can scale with growing demand while ensuring resilience against both traffic spikes and component failures.

