## WEEK 9

## SERVERS

## Understanding Servers
A server is a computing resource that delivers content or applications to client systems. In AWS, servers are provisioned as EC2 instances (Elastic Compute Cloud).

# Key Concepts:
- Instance types are selected based on required CPU, memory, and storage specifications
- Operating systems include various Linux distributions and Windows Server editions
- Billing is usage-based, calculated per hour or per second depending on instance type
- Instances can be stopped and started on demand to optimize costs
- Provides cloud-based compute capacity without physical hardware investment

# Common Applications:
- Web application hosting
- Database hosting
- Data processing workflows
- General-purpose computing tasks

## SCALING AND NAME RESOLUTION

# Scaling Fundamentals
Scaling enables applications to accommodate variable user loads and traffic patterns while maintaining performance and availability.

# Scaling Approaches:
- Vertical Scaling: Increasing individual instance capacity by upgrading to larger instance types
- Horizontal Scaling: Distributing load across multiple instances operating in parallel

# Auto Scaling:
AWS Auto Scaling dynamically adjusts compute capacity based on defined metrics and policies. The service automatically provisions additional instances during demand spikes and removes instances during low-traffic periods to optimize costs.

# Name Resolution (Amazon Route 53):
Route 53 is AWS's managed DNS service that translates domain names into IP addresses. It functions as the authoritative DNS resolver, directing user requests to the appropriate server resources based on configured routing policies.

## SERVERLESS AND CONTAINERS

# Serverless Computing (AWS Lambda):
Serverless architecture abstracts infrastructure management, allowing developers to focus on code rather than server administration. Despite the name, servers exist but are fully managed by the cloud provider.

# Serverless Benefits:
- Eliminates infrastructure maintenance overhead
- Consumption-based pricing model (charged only during code execution)
- Automatic scaling based on request volume
- Ideal for event-driven processing, API endpoints, and scheduled tasks
- 
# Container Services (Amazon ECS, EKS, Fargate):
Containers encapsulate applications with their dependencies, creating portable, consistent runtime environments across different computing environments.

# AWS Container Services:
- ECS (Elastic Container Service): AWS-native container orchestration platform
- EKS (Elastic Kubernetes Service): Managed Kubernetes for organizations using container orchestration
- Fargate: Serverless compute engine for containers, eliminating cluster management

# Selection Criteria:
- Lambda: Event-driven functions, microservices, stateless operations
- Containers: Complex applications, microservices architectures, stateful workloads

## AWS DATABASE SERVICES

# Managed Database Advantages
AWS managed database services provide automated backup management, patch deployment, scaling capabilities, and security controls, reducing operational overhead compared to self-managed database installations.

# Primary Database Services:

# RDS (Relational Database Service):
- Supports MySQL, PostgreSQL, Oracle, SQL Server, and MariaDB engines
- Automated backup and recovery operations
- Suitable for structured data with defined relationships and ACID compliance requirements

# Amazon Aurora:
- AWS-proprietary relational database compatible with MySQL and PostgreSQL
- Enhanced performance and availability compared to standard RDS
- Continuous backup to Amazon S3
- Higher cost offset by improved reliability for mission-critical applications

# DynamoDB:
- Fully managed NoSQL database service
- Single-digit millisecond latency at any scale
- Optimal for key-value storage, mobile backends, and high-velocity data ingestion
- Flexible pricing: on-demand or provisioned capacity modes

# ElastiCache:
- In-memory caching service supporting Redis and Memcached engines
- Reduces database load and improves query response times
- Functions as a high-speed data access layer

# Amazon Redshift:
- Petabyte-scale data warehouse solution
- Optimized for analytical queries and business intelligence workloads
- Not intended for transactional database operations

# Database Selection Framework:
- Relational data with SQL requirements → RDS or Aurora
- High-performance NoSQL requirements → DynamoDB
- Large-scale analytics and reporting → Redshift
- Query performance optimization → ElastiCache
