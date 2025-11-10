

  📝 WEEK 3

  LINUX,NETWORKING

Computers connected together to share information
Like a highway system for data 🚗
Allows devices to communicate
🔑 Key Terms:Network 🕸️

Group of connected devices
Share resources and data
Protocol 📋

Rules for communication
Like a common language computers speak
Example: HTTP, TCP/IP, FTP
Bandwidth 🚀

Speed of data transfer
Measured in Mbps or Gbps
Like width of a highway (more lanes = faster)
Latency ⏱️

Delay in communication
Measured in milliseconds (ms)
Lower is better (faster response)
Router 🔀

Directs traffic between networks
Like a traffic cop
Connects your home to the internet
Switch 🔄

Connects devices within same network
Like a distribution center
Sends data to correct device
Firewall 🔥🧱

Security barrier
Blocks unwanted traffic
Protects your network
📊 Network Types:
LAN (Local Area Network) 🏠

Small area (home, office)
Fast and secure
Example: Your home WiFi



WAN (Wide Area Network) 🌍

Large area (cities, countries)
Connects multiple LANs
Example: The Internet



VPN (Virtual Private Network) 🔐

Secure connection over internet
Encrypts your data
Like a private tunnel


🎯 OSI Model (7 Layers):
Think of it like a mail delivery system 📬
Physical 🔌 → Cables, WiFi signals (the truck)
Data Link 📡 → MAC addresses, switches (local delivery)
Network 🗺️ → IP addresses, routers (route planning)
Transport 🚚 → TCP/UDP, ports (delivery tracking)
Session 🤝 → Maintains connections (meeting appointment)
Presentation 🎨 → Encryption, formatting (wrapping the package)
Application 📱 → HTTP, FTP, email (the actual letter)
🔌 TCP vs UDP:TCP (Transmission Control Protocol) 📦✅

Reliable delivery
Checks if data arrived
Slower but accurate
Example: Web browsing, email
UDP (User Datagram Protocol) 📦⚡

Fast delivery
Doesn't check if data arrived
Faster but can lose data
Example: Video calls, gaming, streaming
🏷️ IP AddressesWhat is an IP Address?

Unique address for each device on network
Like a home address for computers 🏠
Allows devices to find each other
📍 IPv4 (Version 4):

Most common format
Looks like: 192.168.1.100
Four numbers (0-255) separated by dots
About 4.3 billion possible addresses
Running out of addresses 😰
📍 IPv6 (Version 6):

Newer format
Looks like: 2001:0db8:85a3:0000:0000:8a2e:0370:7334
Uses letters and numbers
340 undecillion addresses (almost unlimited!)
Slowly replacing IPv4
🎭 IP Address Classes (IPv4):Class A 🏢

Range: 1.0.0.0 to 126.255.255.255
For huge networks (millions of devices)
First number identifies network
Class B 🏭

Range: 128.0.0.0 to 191.255.255.255
For medium networks (thousands of devices)
First two numbers identify network
Class C 🏪

Range: 192.0.0.0 to 223.255.255.255
For small networks (254 devices)
First three numbers identify network
🔢 Special IP Addresses:
127.0.0.1 → Localhost (your own computer) 🏠
0.0.0.0 → All addresses/any address
255.255.255.255 → Broadcast (send to everyone)
🎯 Subnets & Subnet Masks:Subnet 🗂️

Divides network into smaller sections
Improves security and performance
Like dividing a building into apartments
Subnet Mask 🎭

Identifies which part is network vs device
Common: 255.255.255.0 (Class C)
Shows how many devices can fit
CIDR Notation 📝

Shorter way to write subnet mask
Example: 192.168.1.0/24
/24 means first 24 bits are network
🧮 Example:

IP: 192.168.1.10
Subnet: 255.255.255.0 or /24
Network: 192.168.1.0
Usable IPs: 192.168.1.1 to 192.168.1.254
Total devices: 254
☁️ Networking in AWS🌐 VPC (Virtual Private Cloud):

Your own private network in AWS
Like your own data center in the cloud
Isolated from other customers
Full control over network
🏗️ VPC Components:1. Subnets 🗂️

Sections of your VPC
Can be public or private
Lives in one Availability Zone
Like rooms in your house
2. Internet Gateway (IGW) 🚪🌍

Connects VPC to internet
Allows public access
Like your front door
3. NAT Gateway 🔄

Allows private subnets to access internet
But internet can't access them
One-way street for outgoing traffic
Costs money 💰
4. Route Tables 🗺️

Directions for network traffic
Tells data where to go
Each subnet has a route table
5. Network ACLs 🛡️

Firewall at subnet level
Stateless (checks both ways)
Allow/deny rules by IP
6. Security Groups 🔒

Firewall at instance level
Stateful (remembers connections)
Only allow rules (no deny)
🎯 Public vs Private Subnets:Public Subnet 🌍

Has route to Internet Gateway
Devices get public IPs
Accessible from internet
Use for: Web servers, load balancers
Private Subnet 🔐

No direct internet access
Only private IPs
More secure
Use for: Databases, application servers
📊 Common VPC Setup:
VPC (10.0.0.0/16)
├── Public Subnet (10.0.1.0/24) → IGW → Internet
│   └── Web Server (public IP)
└── Private Subnet (10.0.2.0/24) → NAT → Internet
    └── Database (private IP only)🌍 AWS Regions & AZs in Networking:

VPC spans entire region
Subnets exist in one AZ
Best practice: Use multiple AZs for redundancy
High availability setup
🌐 Public and Private IP Addresses🔓 Public IP Addresses:What are they? 🌍

Visible on the internet
Globally unique
Can be accessed from anywhere
Like your home's street address
Characteristics:

✅ Internet accessible
✅ Routable globally
✅ Must be unique worldwide
❌ Limited supply (expensive)
Use Cases:

Web servers
Email servers
Gaming servers
Anything users access directly
AWS Public IPs:

Assigned to EC2 in public subnet
Can be Elastic IP (static) or auto-assigned (dynamic)
Charged if not attached to running instance
🔒 Private IP Addresses:What are they? 🏠

Only visible within private network
Not accessible from internet
Can be reused in different networks
Like an apartment number (only meaningful inside building)
Private IP Ranges: (Reserved by IANA)

Class A: 10.0.0.0 to 10.255.255.255 (/8)
Class B: 172.16.0.0 to 172.31.255.255 (/12)
Class C: 192.168.0.0 to 192.168.255.255 (/16)
Characteristics:

✅ Free to use
✅ More secure (hidden from internet)
✅ Unlimited within your network
❌ Can't directly access internet
Use Cases:

Internal servers
Databases
Backend applications
Office computers
AWS Private IPs:

Every EC2 instance gets one
Stays with instance until terminated
Free (included)
Used for internal communication
🔄 How They Work Together:Scenario: Web application in AWS
User (Internet) 
    ↓
Public IP (Web Server: 54.123.45.67)
    ↓
Private IP (Web Server: 10.0.1.10)
    ↓
Private IP (Database: 10.0.2.20)

Users access public IP
Web server talks to database using private IPs
Database never exposed to internet
🔄 Dynamic and Static IPs⚡ Dynamic IP Addresses:What is it? 🎲

Changes each time device connects
Assigned temporarily by DHCP server
Like a hotel room number (changes each visit)
DHCP (Dynamic Host Configuration Protocol) 🤖

Automatically assigns IPs
Manages IP pool
Leases IPs for limited time
Renews when expired
Advantages: ✅

Easier to manage (automatic)
No manual configuration
Efficient use of available IPs
Cheaper
Disadvantages: ❌

IP changes over time
Hard to find specific device
Not good for servers
DNS records become outdated
Use Cases:

Home internet connections
Office computers
Mobile devices
Most client devices
In AWS:

EC2 instances get dynamic public IP by default
IP released when instance stops
New IP assigned when restarted
Free (no extra charge)
📌 Static IP Addresses:What is it? 🎯

Never changes
Manually assigned
Always the same address
Like your permanent home address
Advantages: ✅

Predictable and reliable
Easy to find services
Good for servers
DNS stays correct
Remote access works consistently
Disadvantages: ❌

Manual configuration needed
Uses IPs even when not active
More expensive
Administrative overhead
Use Cases:

Web servers
Email servers
VPN endpoints
Printers in office
CCTV cameras
Remote access systems
In AWS - Elastic IP (EIP): 🎯

Static public IPv4 address
Stays yours until you release it
Can reassign to different instances
Important: Charged if NOT attached to running instance! 💰
Free when attached to running EC2
Limit: 5 per region (can request more)
How to use Elastic IP:

Allocate EIP from AWS
Associate with EC2 instance
Instance now has static public IP
Release when no longer needed
🆚 Comparison:FeatureDynamic IPStatic IPChangesYes, frequentlyNo, permanentCostFree/CheapMore expensiveSetupAutomaticManualBest forClientsServersAWSDefault public IPElastic IP🔧 Troubleshooting Commands🐧 Linux/Mac Network Commands:1. ping 🏓

Tests if host is reachable
Measures round-trip time
Uses ICMP protocol

bashping google.com
ping 8.8.8.8
ping -c 4 192.168.1.1  # Send 4 packets only

Output: Time in ms (lower = better)
If fails: Host down or blocking ICMP
2. ifconfig / ip addr 📡

Shows network interfaces
Displays IP addresses
Shows MAC addresses

bashifconfig              # Older command
ip addr show          # Modern command
ip a                  # Short version

Look for: inet (IPv4), inet6 (IPv6)
3. traceroute / tracepath 🗺️

Shows path to destination
Lists all routers along the way
Identifies where delays occur

bashtraceroute google.com
tracepath google.com    # Doesn't need sudo

Each line = one hop (router)
* * * = router not responding
4. netstat 📊

Shows active connections
Lists listening ports
Displays routing table

bashnetstat -tuln         # TCP/UDP listening ports
netstat -rn           # Routing table
netstat -an           # All connections5. ss ⚡

Modern replacement for netstat
Faster and more detailed

bashss -tuln              # Listening ports
ss -s                 # Summary statistics
ss -t                 # TCP connections6. nslookup / dig 🔍

DNS lookup tools
Converts domain to IP
Tests DNS resolution

bashnslookup google.com
dig google.com
dig google.com +short   # Just the IP7. route 🛣️

Shows routing table
Displays gateway

bashroute -n              # Numeric format
ip route show         # Modern version8. curl / wget 📥

Tests HTTP connections
Downloads files

bashcurl https://google.com
curl -I https://google.com    # Headers only
wget https://example.com/file.zip9. telnet 📞

Tests if port is open
Basic connection test

bashtelnet google.com 80
telnet 192.168.1.1 22

Connected: Port is open ✅
Connection refused: Port closed ❌
10. tcpdump 📦

Captures network packets
Analyzes traffic
Requires root access

bashsudo tcpdump -i eth0           # Capture on eth0
sudo tcpdump port 80           # Only HTTP traffic
sudo tcpdump host 192.168.1.1  # Specific host🔍 Troubleshooting Networks🎯 Systematic Troubleshooting Approach:Step 1: Define the Problem 📝

What's not working?
When did it start?
What changed recently?
Is it one device or all devices?
Step 2: Check Physical Layer 🔌

Cables plugged in? ✅
Lights blinking on router/switch? 💡
WiFi enabled? 📶
Device powered on? ⚡
Step 3: Check IP Configuration 🏷️
baship addr show          # Check if IP assigned
ip route show         # Check default gateway

Do you have an IP? (Not 169.254.x.x)
Is subnet mask correct?
Is gateway configured?
Step 4: Test Local Connectivity 🏠
bashping 127.0.0.1        # Test your own machine
ping 192.168.1.1      # Test gateway/router
ping 192.168.1.x      # Test other local device

Success: Local network is working ✅
Fail: Check cables, switch, IP config ❌
Step 5: Test Gateway 🚪
bashping 192.168.1.1      # Ping your router
traceroute 8.8.8.8    # See if packets leave network

Success: Router is reachable ✅
Fail: Router down or misconfigured ❌
Step 6: Test Internet 🌍
bashping 8.8.8.8          # Google DNS (IP-based)
ping google.com       # Domain-based

8.8.8.8 works, google.com fails: DNS problem 🔍
Both fail: No internet connection 🚫
Step 7: Test DNS 🔍
bashnslookup google.com
dig google.com
cat /etc/resolv.conf  # Check DNS servers

Shows which DNS server you're using
Try alternate: 8.8.8.8 (Google) or 1.1.1.1 (Cloudflare)
🚨 Common Network Problems & Solutions:Problem 1: No Internet Connection 🚫

✅ Check cable/WiFi connection
✅ Restart router and device
✅ Check IP address: ip addr
✅ Ping gateway: ping 192.168.1.1
✅ Ping internet: ping 8.8.8.8
✅ Check firewall settings
  else
    echo "Minor"
  fi

Loops:

bash  for i in 1 2 3 4 5; do
    echo "Number $i"
  done

Functions:

bash  greet() {
    echo "Hello $1"
  }
  greet "World"

User input: read -p "Enter name: " NAME
Arguments: $1, $2, $3 (first, second, third argument passed to script)


🎓 Quick Tips

✅ Use sudo for admin tasks (super user do)
✅ Be careful with rm - files are gone forever!
✅ Use Tab for auto-complete - saves time!
✅ Read error messages - they tell you what's wrong
✅ Practice makes perfect - keep typing commands!

Connect using SSH: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html
EC2 Instance Connect: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-connect-methods.html
Session Manager (no SSH needed): https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.html

WEEK 4 NETWORKING, SECURITY

Data Security
Key Concepts:

Defense in depth: Multiple layers of security controls
Shared Responsibility Model: AWS secures infrastructure, you secure your data and applications
Data classification and handling procedures

AWS Links:

AWS Security Best Practices: https://docs.aws.amazon.com/security/
Shared Responsibility Model: https://aws.amazon.com/compliance/shared-responsibility-model/
AWS Security Hub: https://docs.aws.amazon.com/securityhub/


Data Protection Using Encryption
Encryption Types:

At Rest: Data stored on disks (EBS, S3, RDS)
In Transit: Data moving between services (TLS/SSL)
Client-Side: Encrypt before uploading to AWS

AWS Services:

AWS KMS (Key Management Service): Create and manage encryption keys
AWS CloudHSM: Hardware security modules for key storage
S3 encryption: SSE-S3, SSE-KMS, SSE-C
EBS encryption: Automatic encryption for volumes

AWS Links:

AWS KMS Documentation: https://docs.aws.amazon.com/kms/
Encryption at Rest: https://docs.aws.amazon.com/crypto/latest/userguide/awscryp-service-encrypt.html
S3 Encryption: https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingEncryption.html


IAM (Identity and Access Management)
Core Components:

Users: Individual identities with credentials
Groups: Collections of users with shared permissions
Roles: Temporary credentials for services/applications
Policies: JSON documents defining permissions

Best Practices:

Enable MFA on root and privileged accounts
Use roles instead of access keys where possible
Apply least privilege principle
Rotate credentials regularly
Use IAM Access Analyzer

AWS Links:

IAM Documentation: https://docs.aws.amazon.com/iam/
IAM Best Practices: https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html
IAM Policy Examples: https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_examples.html


AWS Compliance and Knowledge
Compliance Programs:

SOC 1/2/3
PCI DSS
HIPAA
GDPR
ISO 27001
FedRAMP

Resources:

AWS Artifact: Access compliance reports and agreements
AWS Compliance Center: Program information
AWS Config: Track resource compliance

AWS Links:

AWS Compliance Programs: https://aws.amazon.com/compliance/programs/
AWS Artifact: https://docs.aws.amazon.com/artifact/
AWS Config: https://docs.aws.amazon.com/config/
Compliance Center: https://aws.amazon.com/financial-services/security-compliance/compliance-center/


AWS CloudTrail
Purpose: Records API calls and account activity for auditing and compliance
Key Features:

Logs all API calls across AWS services
Stores logs in S3 buckets
Integrates with CloudWatch for monitoring
Event history for 90 days (free)
Trail creation for long-term storage

Use Cases:

Security analysis and incident investigation
Compliance auditing
Resource change tracking
Troubleshooting operational issues

AWS Links:

CloudTrail Documentation: https://docs.aws.amazon.com/cloudtrail/
CloudTrail User Guide: https://docs.aws.amazon.com/awscloudtrail/latest/userguide/
CloudTrail Event History: https://docs.aws.amazon.com/awscloudtrail/latest/userguide/view-cloudtrail-events.html


Monitoring an EC2 Instance
CloudWatch Metrics:

Basic Monitoring (5-minute intervals, free): CPU, Network, Disk
Detailed Monitoring (1-minute intervals, paid)
Custom Metrics: Memory, disk space using CloudWatch Agent

Monitoring Tools:

CloudWatch Dashboards: Visual representation
CloudWatch Alarms: Automated notifications
CloudWatch Logs: Application and system logs
AWS Systems Manager: Patch compliance, inventory

Key Metrics to Monitor:

CPUUtilization
NetworkIn/NetworkOut
DiskReadOps/DiskWriteOps
StatusCheckFailed

AWS Links:

EC2 Monitoring: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/monitoring_ec2.html
CloudWatch Metrics: https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/working_with_metrics.html
CloudWatch Agent: https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Install-CloudWatch-Agent.html


Security Best Practices
General Principles:

Implement least privilege access
Enable MFA for all users
Use security groups as virtual firewalls
Encrypt data at rest and in transit
Regular security assessments and penetration testing
Enable logging and monitoring
Automate security responses
Keep systems patched and updated

AWS Security Services:

AWS GuardDuty: Threat detection
AWS Inspector: Vulnerability scanning
AWS Macie: Data discovery and protection
AWS Shield: DDoS protection
AWS WAF: Web application firewall

AWS Links:

AWS Security Best Practices: https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/
AWS Security Documentation: https://docs.aws.amazon.com/security/
Well-Architected Framework: https://aws.amazon.com/architecture/well-architected/


Network Hardening
VPC Security:

Use private subnets for backend resources
Implement Network ACLs (stateless firewall)
Configure Security Groups (stateful firewall)
Use VPC Flow Logs for traffic analysis
Implement NAT Gateway for outbound-only internet access

Security Groups Best Practices:

Deny by default, allow only necessary traffic
Use specific IP ranges, avoid 0.0.0.0/0 where possible
Reference other security groups instead of IPs
Separate groups by function/tier

Network ACL Best Practices:

Add explicit deny rules for known bad actors
Number rules with gaps (100, 200, 300) for future additions
Remember they're stateless (need inbound and outbound rules)

Additional Hardening:

Enable VPC Flow Logs
Use AWS PrivateLink for private connectivity
Implement bastion hosts or AWS Systems Manager Session Manager
Deploy AWS Network Firewall for advanced filtering

AWS Links:

VPC Security: https://docs.aws.amazon.com/vpc/latest/userguide/security.html
Security Groups: https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html
Network ACLs: https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html
VPC Flow Logs: https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs.html


Numeric Data Types
Common Numeric Types in Databases:
Integer Types:

TINYINT: 1 byte (-128 to 127)
SMALLINT: 2 bytes (-32,768 to 32,767)
MEDIUMINT: 3 bytes (-8,388,608 to 8,388,607)
INT/INTEGER: 4 bytes (-2.1B to 2.1B)
BIGINT: 8 bytes (very large range)

Decimal Types:

DECIMAL(p,s): Fixed precision, exact values (e.g., DECIMAL(10,2) for currency)
NUMERIC: Same as DECIMAL

Floating Point:

FLOAT: 4 bytes, approximate values
DOUBLE: 8 bytes, more precision than FLOAT

AWS Database Numeric Types:
Amazon RDS/Aurora (MySQL/PostgreSQL):

Supports all standard SQL numeric types
Choose DECIMAL for financial calculations (exact)
Use INT types for IDs and counters
FLOAT/DOUBLE for scientific calculations

Amazon DynamoDB:

Number type: Up to 38 digits of precision
Stores as variable-length encoded format
No distinction between integer and decimal

Amazon Redshift:

SMALLINT, INTEGER, BIGINT
DECIMAL(precision, scale)
REAL (4 bytes)
DOUBLE PRECISION (8 bytes)

Best Practices:

Use smallest data type that fits your needs (saves storage)
DECIMAL for money (avoids rounding errors)
INT for foreign keys and IDs
Consider unsigned for values that are never negative

AWS Links:

RDS Data Types: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_MySQL.html#MySQL.Concepts.General.Datatype
DynamoDB Data Types: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.NamingRulesDataTypes.html
Redshift Data Types: https://docs.aws.amazon.com/redshift/latest/dg/c_Supported_data_types.html

WEEK 5 DATABASES

Database Notes with AWS Support Links
Introduction to Databases
What is a Database?
A database is an organized collection of structured data stored electronically in a computer system. Databases are managed by Database Management Systems (DBMS) that allow users to create, read, update, and delete data efficiently.
Types of Databases:
Relational Databases (SQL):

Data organized in tables with rows and columns
Uses Structured Query Language (SQL) for queries
Enforces ACID properties (Atomicity, Consistency, Isolation, Durability)
Supports complex relationships between tables using foreign keys
Examples: MySQL, PostgreSQL, Oracle, SQL Server
Best for: Structured data, complex queries, transactions

Non-Relational Databases (NoSQL):

Flexible schema designs
Horizontal scaling capabilities
Types include: Key-value, Document, Column-family, Graph
Examples: MongoDB, Cassandra, Redis, DynamoDB
Best for: Unstructured data, high scalability, rapid development

Key Database Concepts:

Schema: Structure that defines how data is organized
Primary Key: Unique identifier for each record
Foreign Key: Links tables together for relationships
Index: Improves query performance by creating quick lookup paths
Normalization: Process of organizing data to reduce redundancy
Transaction: Group of operations that execute as a single unit


Data Retrieval
SQL SELECT Statement:
The fundamental command for retrieving data from relational databases.
Basic Syntax:
sqlSELECT column1, column2 FROM table_name;
SELECT * FROM table_name;  -- Retrieves all columns
Filtering Data with WHERE:
sqlSELECT * FROM customers WHERE country = 'USA';
SELECT * FROM products WHERE price > 100;
SELECT * FROM orders WHERE order_date >= '2024-01-01';
Sorting Results:
sqlSELECT * FROM employees ORDER BY last_name ASC;
SELECT * FROM products ORDER BY price DESC;
Joining Tables:
sql-- Inner Join: Returns matching records from both tables
SELECT orders.order_id, customers.customer_name
FROM orders
INNER JOIN customers ON orders.customer_id = customers.customer_id;

-- Left Join: Returns all records from left table and matching from right
SELECT customers.customer_name, orders.order_id
FROM customers
LEFT JOIN orders ON customers.customer_id = orders.customer_id;
Aggregate Functions:
sqlSELECT COUNT(*) FROM orders;
SELECT AVG(price) FROM products;
SELECT SUM(amount) FROM sales;
SELECT MAX(salary) FROM employees;
SELECT MIN(age) FROM users;
Grouping Data:
sqlSELECT country, COUNT(*) as customer_count
FROM customers
GROUP BY country
HAVING COUNT(*) > 5;
NoSQL Data Retrieval:
NoSQL databases use different query methods depending on the type:

Key-Value: Direct key lookup (fastest)
Document: Query by document fields using JSON-like syntax
DynamoDB: Uses partition keys and sort keys for efficient retrieval


Amazon Aurora
What is Amazon Aurora?
Amazon Aurora is a MySQL and PostgreSQL-compatible relational database built for the cloud. It combines the performance and availability of high-end commercial databases with the simplicity and cost-effectiveness of open-source databases.
Key Features:
Performance:

Up to 5x faster than standard MySQL
Up to 3x faster than standard PostgreSQL
Automated performance tuning and monitoring
Read replicas with minimal lag

High Availability:

99.99% availability SLA
Automatic failover in less than 30 seconds
Data replicated 6 ways across 3 Availability Zones
Continuous backup to Amazon S3
Point-in-time recovery up to the last 5 minutes

Scalability:

Storage auto-scales up to 128 TB
Up to 15 read replicas
Global database for low-latency global reads
Aurora Serverless for automatic scaling based on demand

Security:

Encryption at rest using AWS KMS
Encryption in transit using SSL
Network isolation with Amazon VPC
IAM database authentication
Automated backups, snapshots, and replicas

Use Cases:

Enterprise applications requiring high availability
SaaS applications with variable workloads
Web and mobile gaming applications
Online transaction processing (OLTP)
Applications needing MySQL/PostgreSQL compatibility

Aurora Serverless:

On-demand, auto-scaling configuration
Automatically starts up, shuts down, and scales capacity
Pay only for database resources consumed
Ideal for infrequent, intermittent, or unpredictable workloads


Amazon DynamoDB
What is Amazon DynamoDB?
Amazon DynamoDB is a fully managed NoSQL database service that provides fast and predictable performance with seamless scalability. It's a key-value and document database.
Key Features:
Performance:

Single-digit millisecond latency at any scale
Supports millions of requests per second
Automatic multi-region replication
In-memory caching with DynamoDB Accelerator (DAX)

Fully Managed:

No servers to provision or manage
Automatic scaling up and down
Built-in security, backup, and restore
Point-in-time recovery
Global tables for multi-region applications

Data Model:

Tables: Collection of items (similar to rows)
Items: Collection of attributes (similar to records)
Attributes: Fundamental data elements (name-value pairs)
Primary Key: Required, can be partition key only or partition + sort key
Secondary Indexes: Query data using alternate keys

Read/Write Capacity Modes:
On-Demand Mode:

Pay per request
No capacity planning needed
Handles unpredictable workloads
Good for new applications

Provisioned Mode:

Specify read/write capacity units
More cost-effective for predictable traffic
Auto Scaling available
Reserved capacity for additional savings

DynamoDB Features:
DynamoDB Streams:

Capture item-level changes in tables
Integration with AWS Lambda for triggers
Use cases: Auditing, analytics, replication

Global Tables:

Multi-region, fully replicated tables
Sub-second replication between regions
Active-active configuration
Disaster recovery and high availability

Transactions:

ACID compliance across multiple items and tables
All-or-nothing operations
Supports complex business logic

Use Cases:

Mobile and web applications
Gaming leaderboards and session management
IoT applications with high write throughput
Real-time bidding and ad tech
Shopping carts and user profiles
Serverless applications with Lambda

Best Practices:

Design for uniform data distribution across partition keys
Use composite keys for hierarchical data
Implement efficient query patterns
Use sparse indexes for selective queries
Enable point-in-time recovery for critical data


Selecting a Database
Factors to Consider:
1. Data Structure:

Structured, relational data → Relational databases (RDS, Aurora)
Unstructured, flexible schema → NoSQL (DynamoDB, DocumentDB)
Key-value pairs → DynamoDB, ElastiCache
Graph relationships → Amazon Neptune
Time-series data → Amazon Timestream

2. Query Patterns:

Complex joins and transactions → Aurora, RDS
Simple lookups by key → DynamoDB
Full-text search → Amazon OpenSearch
Analytics and reporting → Redshift, Athena

3. Scale Requirements:

Predictable, moderate scale → RDS
Massive scale, high throughput → DynamoDB
Read-heavy workloads → Aurora with read replicas, ElastiCache
Write-heavy workloads → DynamoDB

4. Performance Needs:

Sub-millisecond latency → DynamoDB with DAX, ElastiCache
Consistent performance → Aurora, DynamoDB
Batch processing → Redshift

5. Availability Requirements:

Mission-critical, 99.99% uptime → Aurora, DynamoDB Global Tables
Standard availability → RDS Multi-AZ
Regional resilience → Multi-region deployments

6. Cost Considerations:

Predictable workloads → RDS Reserved Instances, DynamoDB Provisioned
Variable workloads → Aurora Serverless, DynamoDB On-Demand
Development/testing → RDS with smaller instances

AWS Database Decision Tree:
Relational → Amazon RDS or Aurora

Need MySQL/PostgreSQL compatibility? → Aurora
Need Oracle/SQL Server? → RDS
Variable workload? → Aurora Serverless

NoSQL → DynamoDB or DocumentDB

Key-value or simple document? → DynamoDB
MongoDB compatibility needed? → DocumentDB

Specialized:

In-memory caching → ElastiCache (Redis/Memcached)
Data warehousing → Redshift
Graph database → Neptune
Ledger database → QLDB
Time-series → Timestream


Inserting Data
SQL INSERT Statements:
Basic Insert:
sql-- Insert single row
INSERT INTO customers (customer_id, name, email, country)
VALUES (1, 'John Doe', 'john@example.com', 'USA');

-- Insert multiple rows
INSERT INTO products (product_id, name, price, category)
VALUES 
    (1, 'Laptop', 999.99, 'Electronics'),
    (2, 'Mouse', 29.99, 'Electronics'),
    (3, 'Desk', 299.99, 'Furniture');
Insert with SELECT (Copy data):
sqlINSERT INTO archive_orders
SELECT * FROM orders
WHERE order_date < '2023-01-01';
Insert Default Values:
sqlINSERT INTO logs (timestamp, message)
VALUES (DEFAULT, 'System started');
Best Practices for SQL Inserts:

Use prepared statements to prevent SQL injection
Batch inserts for better performance
Use transactions for multiple related inserts
Validate data before insertion
Handle duplicate key errors appropriately

DynamoDB Data Insertion:
PutItem Operation:
Used to insert a single item or replace an existing item.
Example (AWS SDK for Python - Boto3):
pythonimport boto3

dynamodb = boto3.resource('dynamodb')
table = dynamodb.Table('Customers')

# Insert single item
response = table.put_item(
    Item={
        'customer_id': '12345',
        'name': 'John Doe',
        'email': 'john@example.com',
        'registration_date': '2024-01-15',
        'address': {
            'street': '123 Main St',
            'city': 'Seattle',
            'state': 'WA'
        }
    }
)
BatchWriteItem Operation:
Insert up to 25 items in a single request for better efficiency.
pythonwith table.batch_writer() as batch:
    batch.put_item(Item={'customer_id': '1', 'name': 'Alice'})
    batch.put_item(Item={'customer_id': '2', 'name': 'Bob'})
    batch.put_item(Item={'customer_id': '3', 'name': 'Charlie'})
Conditional Inserts:
Insert only if item doesn't exist:
pythonresponse = table.put_item(
    Item={'customer_id': '12345', 'name': 'John Doe'},
    ConditionExpression='attribute_not_exists(customer_id)'
)
DynamoDB Insert Best Practices:

Design partition keys for even distribution
Use batch operations for multiple items
Implement error handling and retries
Use conditional writes to prevent overwrites
Monitor write capacity consumption
Consider using DynamoDB Streams for downstream processing
Use transactions for atomic operations across items

Data Validation:

Validate data types and formats before insertion
Enforce required fields
Check for data integrity constraints
Sanitize user input
Use application-level validation

Performance Optimization:

Use bulk/batch operations when possible
Implement connection pooling
Use asynchronous writes when appropriate
Monitor database performance metrics
Index commonly queried fields


AWS Documentation Links
General Database Information:

AWS Databases Overview: https://aws.amazon.com/products/databases/
What is a Database: https://aws.amazon.com/what-is/database/
Choosing an AWS Database: https://aws.amazon.com/products/databases/choose-your-database/
AWS Database Blog: https://aws.amazon.com/blogs/database/
Database Freedom Program: https://aws.amazon.com/products/databases/freedom/

Amazon RDS (Relational Database Service):

Amazon RDS Documentation: https://docs.aws.amazon.com/rds/
Amazon RDS User Guide: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/
RDS Getting Started: https://aws.amazon.com/rds/getting-started/
RDS FAQs: https://aws.amazon.com/rds/faqs/

Amazon Aurora:

Amazon Aurora Documentation: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/
Amazon Aurora Product Page: https://aws.amazon.com/rds/aurora/
Aurora MySQL Reference: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.AuroraMySQL.html
Aurora PostgreSQL Reference: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.AuroraPostgreSQL.html
Aurora Serverless: https://aws.amazon.com/rds/aurora/serverless/
Aurora Global Database: https://aws.amazon.com/rds/aurora/global-database/
Aurora FAQs: https://aws.amazon.com/rds/aurora/faqs/

Amazon DynamoDB:

DynamoDB Documentation: https://docs.aws.amazon.com/dynamodb/
DynamoDB Developer Guide: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/
DynamoDB Getting Started: https://aws.amazon.com/dynamodb/getting-started/
DynamoDB Data Modeling: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-modeling-nosql.html
DynamoDB Best Practices: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/best-practices.html
DynamoDB Streams: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Streams.html
DynamoDB Global Tables: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GlobalTables.html
DynamoDB Accelerator (DAX): https://aws.amazon.com/dynamodb/dax/
DynamoDB FAQs: https://aws.amazon.com/dynamodb/faqs/

SQL and Query Documentation:

RDS SQL Reference (MySQL): https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html
RDS SQL Reference (PostgreSQL): https://www.postgresql.org/docs/current/sql.html
Aurora MySQL SQL Reference: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.AuroraMySQL.html
Query Performance Tuning: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_BestPractices.html

DynamoDB API Operations:

PutItem API: https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_PutItem.html
BatchWriteItem API: https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_BatchWriteItem.html
GetItem API: https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_GetItem.html
Query API: https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_Query.html
Scan API: https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_Scan.html

Other AWS Database Services:

Amazon DocumentDB (MongoDB-compatible): https://aws.amazon.com/documentdb/
Amazon Neptune (Graph Database): https://aws.amazon.com/neptune/
Amazon Redshift (Data Warehouse): https://aws.amazon.com/redshift/
Amazon ElastiCache (In-Memory): https://aws.amazon.com/elasticache/
Amazon Timestream (Time-Series): https://aws.amazon.com/timestream/
Amazon QLDB (Ledger): https://aws.amazon.com/qldb/

Migration and Tools:

AWS Database Migration Service: https://aws.amazon.com/dms/
AWS Schema Conversion Tool: https://aws.amazon.com/dms/schema-conversion-tool/
Database Migration Guides: https://docs.aws.amazon.com/dms/latest/userguide/

Training and Best Practices:

Database Learning Path: https://aws.amazon.com/training/learn-about/databases/
AWS Well-Architected Framework (Database): https://docs.aws.amazon.com/wellarchitected/latest/framework/
Database Whitepapers: https://aws.amazon.com/whitepapers/?whitepapers-main.sort-by=item.additionalFields.sortDate&whitepapers-main.sort-order=desc&awsf.whitepapers-content-type=*all&awsf.whitepapers-tech-category=tech-category%23databases




