WEEK 4 NETWORKING, SECURITY

Data Security Key Concepts:

Defense in depth: Multiple layers of security controls Shared Responsibility Model: AWS secures infrastructure, you secure your data and applications Data classification and handling procedures

AWS Links:

AWS Security Best Practices: https://docs.aws.amazon.com/security/ Shared Responsibility Model: https://aws.amazon.com/compliance/shared-responsibility-model/ AWS Security Hub: https://docs.aws.amazon.com/securityhub/

Data Protection Using Encryption Encryption Types:

At Rest: Data stored on disks (EBS, S3, RDS) In Transit: Data moving between services (TLS/SSL) Client-Side: Encrypt before uploading to AWS

AWS Services:

AWS KMS (Key Management Service): Create and manage encryption keys AWS CloudHSM: Hardware security modules for key storage S3 encryption: SSE-S3, SSE-KMS, SSE-C EBS encryption: Automatic encryption for volumes

AWS Links:

AWS KMS Documentation: https://docs.aws.amazon.com/kms/ Encryption at Rest: https://docs.aws.amazon.com/crypto/latest/userguide/awscryp-service-encrypt.html S3 Encryption: https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingEncryption.html

IAM (Identity and Access Management) Core Components:

Users: Individual identities with credentials Groups: Collections of users with shared permissions Roles: Temporary credentials for services/applications Policies: JSON documents defining permissions

Best Practices:

Enable MFA on root and privileged accounts Use roles instead of access keys where possible Apply least privilege principle Rotate credentials regularly Use IAM Access Analyzer

AWS Links:

IAM Documentation: https://docs.aws.amazon.com/iam/ IAM Best Practices: https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html IAM Policy Examples: https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_examples.html

AWS Compliance and Knowledge Compliance Programs:

SOC 1/2/3 PCI DSS HIPAA GDPR ISO 27001 FedRAMP

Resources:

AWS Artifact: Access compliance reports and agreements AWS Compliance Center: Program information AWS Config: Track resource compliance

AWS Links:

AWS Compliance Programs: https://aws.amazon.com/compliance/programs/ AWS Artifact: https://docs.aws.amazon.com/artifact/ AWS Config: https://docs.aws.amazon.com/config/ Compliance Center: https://aws.amazon.com/financial-services/security-compliance/compliance-center/

AWS CloudTrail Purpose: Records API calls and account activity for auditing and compliance Key Features:

Logs all API calls across AWS services Stores logs in S3 buckets Integrates with CloudWatch for monitoring Event history for 90 days (free) Trail creation for long-term storage

Use Cases:

Security analysis and incident investigation Compliance auditing Resource change tracking Troubleshooting operational issues

AWS Links:

CloudTrail Documentation: https://docs.aws.amazon.com/cloudtrail/ CloudTrail User Guide: https://docs.aws.amazon.com/awscloudtrail/latest/userguide/ CloudTrail Event History: https://docs.aws.amazon.com/awscloudtrail/latest/userguide/view-cloudtrail-events.html

Monitoring an EC2 Instance CloudWatch Metrics:

Basic Monitoring (5-minute intervals, free): CPU, Network, Disk Detailed Monitoring (1-minute intervals, paid) Custom Metrics: Memory, disk space using CloudWatch Agent

Monitoring Tools:

CloudWatch Dashboards: Visual representation CloudWatch Alarms: Automated notifications CloudWatch Logs: Application and system logs AWS Systems Manager: Patch compliance, inventory

Key Metrics to Monitor:

CPUUtilization NetworkIn/NetworkOut DiskReadOps/DiskWriteOps StatusCheckFailed

AWS Links:

EC2 Monitoring: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/monitoring_ec2.html CloudWatch Metrics: https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/working_with_metrics.html CloudWatch Agent: https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Install-CloudWatch-Agent.html

Security Best Practices General Principles:

Implement least privilege access Enable MFA for all users Use security groups as virtual firewalls Encrypt data at rest and in transit Regular security assessments and penetration testing Enable logging and monitoring Automate security responses Keep systems patched and updated

AWS Security Services:

AWS GuardDuty: Threat detection AWS Inspector: Vulnerability scanning AWS Macie: Data discovery and protection AWS Shield: DDoS protection AWS WAF: Web application firewall

AWS Links:

AWS Security Best Practices: https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/ AWS Security Documentation: https://docs.aws.amazon.com/security/ Well-Architected Framework: https://aws.amazon.com/architecture/well-architected/

Network Hardening VPC Security:

Use private subnets for backend resources Implement Network ACLs (stateless firewall) Configure Security Groups (stateful firewall) Use VPC Flow Logs for traffic analysis Implement NAT Gateway for outbound-only internet access

Security Groups Best Practices:

Deny by default, allow only necessary traffic Use specific IP ranges, avoid 0.0.0.0/0 where possible Reference other security groups instead of IPs Separate groups by function/tier

Network ACL Best Practices:

Add explicit deny rules for known bad actors Number rules with gaps (100, 200, 300) for future additions Remember they're stateless (need inbound and outbound rules)

Additional Hardening:

Enable VPC Flow Logs Use AWS PrivateLink for private connectivity Implement bastion hosts or AWS Systems Manager Session Manager Deploy AWS Network Firewall for advanced filtering

AWS Links:

VPC Security: https://docs.aws.amazon.com/vpc/latest/userguide/security.html Security Groups: https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html Network ACLs: https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html VPC Flow Logs: https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs.html

Numeric Data Types Common Numeric Types in Databases: Integer Types:

TINYINT: 1 byte (-128 to 127) SMALLINT: 2 bytes (-32,768 to 32,767) MEDIUMINT: 3 bytes (-8,388,608 to 8,388,607) INT/INTEGER: 4 bytes (-2.1B to 2.1B) BIGINT: 8 bytes (very large range)

Decimal Types:

DECIMAL(p,s): Fixed precision, exact values (e.g., DECIMAL(10,2) for currency) NUMERIC: Same as DECIMAL

Floating Point:

FLOAT: 4 bytes, approximate values DOUBLE: 8 bytes, more precision than FLOAT

AWS Database Numeric Types: Amazon RDS/Aurora (MySQL/PostgreSQL):

Supports all standard SQL numeric types Choose DECIMAL for financial calculations (exact) Use INT types for IDs and counters FLOAT/DOUBLE for scientific calculations

Amazon DynamoDB:

Number type: Up to 38 digits of precision Stores as variable-length encoded format No distinction between integer and decimal

Amazon Redshift:

SMALLINT, INTEGER, BIGINT DECIMAL(precision, scale) REAL (4 bytes) DOUBLE PRECISION (8 bytes)

Best Practices:

Use smallest data type that fits your needs (saves storage) DECIMAL for money (avoids rounding errors) INT for foreign keys and IDs Consider unsigned for values that are never negative

AWS Links:

RDS Data Types: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_MySQL.html#MySQL.Concepts.General.Datatype DynamoDB Data Types: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.NamingRulesDataTypes.html Redshift Data Types: https://docs.aws.amazon.com/redshift/latest/dg/c_Supported_data_types.html
