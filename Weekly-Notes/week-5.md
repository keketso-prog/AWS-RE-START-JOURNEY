WEEK 5 DATABASES

Database Notes with AWS Support Links Introduction to Databases What is a Database? A database is an organized collection of structured data stored electronically in a computer system. Databases are managed by Database Management Systems (DBMS) that allow users to create, read, update, and delete data efficiently. Types of Databases: Relational Databases (SQL):

Data organized in tables with rows and columns Uses Structured Query Language (SQL) for queries Enforces ACID properties (Atomicity, Consistency, Isolation, Durability) Supports complex relationships between tables using foreign keys Examples: MySQL, PostgreSQL, Oracle, SQL Server Best for: Structured data, complex queries, transactions

Non-Relational Databases (NoSQL):

Flexible schema designs Horizontal scaling capabilities Types include: Key-value, Document, Column-family, Graph Examples: MongoDB, Cassandra, Redis, DynamoDB Best for: Unstructured data, high scalability, rapid development

Key Database Concepts:

Schema: Structure that defines how data is organized Primary Key: Unique identifier for each record Foreign Key: Links tables together for relationships Index: Improves query performance by creating quick lookup paths Normalization: Process of organizing data to reduce redundancy Transaction: Group of operations that execute as a single unit

Data Retrieval SQL SELECT Statement: The fundamental command for retrieving data from relational databases. Basic Syntax: sqlSELECT column1, column2 FROM table_name; SELECT * FROM table_name; -- Retrieves all columns Filtering Data with WHERE: sqlSELECT * FROM customers WHERE country = 'USA'; SELECT * FROM products WHERE price > 100; SELECT * FROM orders WHERE order_date >= '2024-01-01'; Sorting Results: sqlSELECT * FROM employees ORDER BY last_name ASC; SELECT * FROM products ORDER BY price DESC; Joining Tables: sql-- Inner Join: Returns matching records from both tables SELECT orders.order_id, customers.customer_name FROM orders INNER JOIN customers ON orders.customer_id = customers.customer_id;

-- Left Join: Returns all records from left table and matching from right SELECT customers.customer_name, orders.order_id FROM customers LEFT JOIN orders ON customers.customer_id = orders.customer_id; Aggregate Functions: sqlSELECT COUNT() FROM orders; SELECT AVG(price) FROM products; SELECT SUM(amount) FROM sales; SELECT MAX(salary) FROM employees; SELECT MIN(age) FROM users; Grouping Data: sqlSELECT country, COUNT() as customer_count FROM customers GROUP BY country HAVING COUNT(*) > 5; NoSQL Data Retrieval: NoSQL databases use different query methods depending on the type:

Key-Value: Direct key lookup (fastest) Document: Query by document fields using JSON-like syntax DynamoDB: Uses partition keys and sort keys for efficient retrieval

Amazon Aurora What is Amazon Aurora? Amazon Aurora is a MySQL and PostgreSQL-compatible relational database built for the cloud. It combines the performance and availability of high-end commercial databases with the simplicity and cost-effectiveness of open-source databases. Key Features: Performance:

Up to 5x faster than standard MySQL Up to 3x faster than standard PostgreSQL Automated performance tuning and monitoring Read replicas with minimal lag

High Availability:

99.99% availability SLA Automatic failover in less than 30 seconds Data replicated 6 ways across 3 Availability Zones Continuous backup to Amazon S3 Point-in-time recovery up to the last 5 minutes

Scalability:

Storage auto-scales up to 128 TB Up to 15 read replicas Global database for low-latency global reads Aurora Serverless for automatic scaling based on demand

Security:

Encryption at rest using AWS KMS Encryption in transit using SSL Network isolation with Amazon VPC IAM database authentication Automated backups, snapshots, and replicas

Use Cases:

Enterprise applications requiring high availability SaaS applications with variable workloads Web and mobile gaming applications Online transaction processing (OLTP) Applications needing MySQL/PostgreSQL compatibility

Aurora Serverless:

On-demand, auto-scaling configuration Automatically starts up, shuts down, and scales capacity Pay only for database resources consumed Ideal for infrequent, intermittent, or unpredictable workloads

Amazon DynamoDB What is Amazon DynamoDB? Amazon DynamoDB is a fully managed NoSQL database service that provides fast and predictable performance with seamless scalability. It's a key-value and document database. Key Features: Performance:

Single-digit millisecond latency at any scale Supports millions of requests per second Automatic multi-region replication In-memory caching with DynamoDB Accelerator (DAX)

Fully Managed:

No servers to provision or manage Automatic scaling up and down Built-in security, backup, and restore Point-in-time recovery Global tables for multi-region applications

Data Model:

Tables: Collection of items (similar to rows) Items: Collection of attributes (similar to records) Attributes: Fundamental data elements (name-value pairs) Primary Key: Required, can be partition key only or partition + sort key Secondary Indexes: Query data using alternate keys

Read/Write Capacity Modes: On-Demand Mode:

Pay per request No capacity planning needed Handles unpredictable workloads Good for new applications

Provisioned Mode:

Specify read/write capacity units More cost-effective for predictable traffic Auto Scaling available Reserved capacity for additional savings

DynamoDB Features: DynamoDB Streams:

Capture item-level changes in tables Integration with AWS Lambda for triggers Use cases: Auditing, analytics, replication

Global Tables:

Multi-region, fully replicated tables Sub-second replication between regions Active-active configuration Disaster recovery and high availability

Transactions:

ACID compliance across multiple items and tables All-or-nothing operations Supports complex business logic

Use Cases:

Mobile and web applications Gaming leaderboards and session management IoT applications with high write throughput Real-time bidding and ad tech Shopping carts and user profiles Serverless applications with Lambda

Best Practices:

Design for uniform data distribution across partition keys Use composite keys for hierarchical data Implement efficient query patterns Use sparse indexes for selective queries Enable point-in-time recovery for critical data

Selecting a Database Factors to Consider:

Data Structure:
Structured, relational data → Relational databases (RDS, Aurora) Unstructured, flexible schema → NoSQL (DynamoDB, DocumentDB) Key-value pairs → DynamoDB, ElastiCache Graph relationships → Amazon Neptune Time-series data → Amazon Timestream

Query Patterns:
Complex joins and transactions → Aurora, RDS Simple lookups by key → DynamoDB Full-text search → Amazon OpenSearch Analytics and reporting → Redshift, Athena

Scale Requirements:
Predictable, moderate scale → RDS Massive scale, high throughput → DynamoDB Read-heavy workloads → Aurora with read replicas, ElastiCache Write-heavy workloads → DynamoDB

Performance Needs:
Sub-millisecond latency → DynamoDB with DAX, ElastiCache Consistent performance → Aurora, DynamoDB Batch processing → Redshift

Availability Requirements:
Mission-critical, 99.99% uptime → Aurora, DynamoDB Global Tables Standard availability → RDS Multi-AZ Regional resilience → Multi-region deployments

Cost Considerations:
Predictable workloads → RDS Reserved Instances, DynamoDB Provisioned Variable workloads → Aurora Serverless, DynamoDB On-Demand Development/testing → RDS with smaller instances

AWS Database Decision Tree: Relational → Amazon RDS or Aurora

Need MySQL/PostgreSQL compatibility? → Aurora Need Oracle/SQL Server? → RDS Variable workload? → Aurora Serverless

NoSQL → DynamoDB or DocumentDB

Key-value or simple document? → DynamoDB MongoDB compatibility needed? → DocumentDB

Specialized:

In-memory caching → ElastiCache (Redis/Memcached) Data warehousing → Redshift Graph database → Neptune Ledger database → QLDB Time-series → Timestream

Inserting Data SQL INSERT Statements: Basic Insert: sql-- Insert single row INSERT INTO customers (customer_id, name, email, country) VALUES (1, 'John Doe', 'john@example.com', 'USA');

-- Insert multiple rows INSERT INTO products (product_id, name, price, category) VALUES (1, 'Laptop', 999.99, 'Electronics'), (2, 'Mouse', 29.99, 'Electronics'), (3, 'Desk', 299.99, 'Furniture'); Insert with SELECT (Copy data): sqlINSERT INTO archive_orders SELECT * FROM orders WHERE order_date < '2023-01-01'; Insert Default Values: sqlINSERT INTO logs (timestamp, message) VALUES (DEFAULT, 'System started'); Best Practices for SQL Inserts:

Use prepared statements to prevent SQL injection Batch inserts for better performance Use transactions for multiple related inserts Validate data before insertion Handle duplicate key errors appropriately

DynamoDB Data Insertion: PutItem Operation: Used to insert a single item or replace an existing item. Example (AWS SDK for Python - Boto3): pythonimport boto3

dynamodb = boto3.resource('dynamodb') table = dynamodb.Table('Customers')

Insert single item
response = table.put_item( Item={ 'customer_id': '12345', 'name': 'John Doe', 'email': 'john@example.com', 'registration_date': '2024-01-15', 'address': { 'street': '123 Main St', 'city': 'Seattle', 'state': 'WA' } } ) BatchWriteItem Operation: Insert up to 25 items in a single request for better efficiency. pythonwith table.batch_writer() as batch: batch.put_item(Item={'customer_id': '1', 'name': 'Alice'}) batch.put_item(Item={'customer_id': '2', 'name': 'Bob'}) batch.put_item(Item={'customer_id': '3', 'name': 'Charlie'}) Conditional Inserts: Insert only if item doesn't exist: pythonresponse = table.put_item( Item={'customer_id': '12345', 'name': 'John Doe'}, ConditionExpression='attribute_not_exists(customer_id)' ) DynamoDB Insert Best Practices:

Design partition keys for even distribution Use batch operations for multiple items Implement error handling and retries Use conditional writes to prevent overwrites Monitor write capacity consumption Consider using DynamoDB Streams for downstream processing Use transactions for atomic operations across items

Data Validation:

Validate data types and formats before insertion Enforce required fields Check for data integrity constraints Sanitize user input Use application-level validation

Performance Optimization:

Use bulk/batch operations when possible Implement connection pooling Use asynchronous writes when appropriate Monitor database performance metrics Index commonly queried fields

AWS Documentation Links General Database Information:

AWS Databases Overview: https://aws.amazon.com/products/databases/ What is a Database: https://aws.amazon.com/what-is/database/ Choosing an AWS Database: https://aws.amazon.com/products/databases/choose-your-database/ AWS Database Blog: https://aws.amazon.com/blogs/database/ Database Freedom Program: https://aws.amazon.com/products/databases/freedom/

Amazon RDS (Relational Database Service):

Amazon RDS Documentation: https://docs.aws.amazon.com/rds/ Amazon RDS User Guide: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/ RDS Getting Started: https://aws.amazon.com/rds/getting-started/ RDS FAQs: https://aws.amazon.com/rds/faqs/

Amazon Aurora:

Amazon Aurora Documentation: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/ Amazon Aurora Product Page: https://aws.amazon.com/rds/aurora/ Aurora MySQL Reference: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.AuroraMySQL.html Aurora PostgreSQL Reference: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.AuroraPostgreSQL.html Aurora Serverless: https://aws.amazon.com/rds/aurora/serverless/ Aurora Global Database: https://aws.amazon.com/rds/aurora/global-database/ Aurora FAQs: https://aws.amazon.com/rds/aurora/faqs/

Amazon DynamoDB:

DynamoDB Documentation: https://docs.aws.amazon.com/dynamodb/ DynamoDB Developer Guide: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ DynamoDB Getting Started: https://aws.amazon.com/dynamodb/getting-started/ DynamoDB Data Modeling: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-modeling-nosql.html DynamoDB Best Practices: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/best-practices.html DynamoDB Streams: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Streams.html DynamoDB Global Tables: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GlobalTables.html DynamoDB Accelerator (DAX): https://aws.amazon.com/dynamodb/dax/ DynamoDB FAQs: https://aws.amazon.com/dynamodb/faqs/

SQL and Query Documentation:

RDS SQL Reference (MySQL): https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html RDS SQL Reference (PostgreSQL): https://www.postgresql.org/docs/current/sql.html Aurora MySQL SQL Reference: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.AuroraMySQL.html Query Performance Tuning: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_BestPractices.html

DynamoDB API Operations:

PutItem API: https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_PutItem.html BatchWriteItem API: https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_BatchWriteItem.html GetItem API: https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_GetItem.html Query API: https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_Query.html Scan API: https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_Scan.html

Other AWS Database Services:

Amazon DocumentDB (MongoDB-compatible): https://aws.amazon.com/documentdb/ Amazon Neptune (Graph Database): https://aws.amazon.com/neptune/ Amazon Redshift (Data Warehouse): https://aws.amazon.com/redshift/ Amazon ElastiCache (In-Memory): https://aws.amazon.com/elasticache/ Amazon Timestream (Time-Series): https://aws.amazon.com/timestream/ Amazon QLDB (Ledger): https://aws.amazon.com/qldb/

Migration and Tools:

AWS Database Migration Service: https://aws.amazon.com/dms/ AWS Schema Conversion Tool: https://aws.amazon.com/dms/schema-conversion-tool/ Database Migration Guides: https://docs.aws.amazon.com/dms/latest/userguide/

Training and Best Practices:

Database Learning Path: https://aws.amazon.com/training/learn-about/databases/ AWS Well-Architected Framework (Database): https://docs.aws.amazon.com/wellarchitected/latest/framework/ Database Whitepapers: https://aws.amazon.com/whitepapers/?whitepapers-main.sort-by=item.additionalFields.sortDate&whitepapers-main.sort-order=desc&awsf.whitepapers-content-type=*all&awsf.whitepapers-tech-category=tech-category%23databases
