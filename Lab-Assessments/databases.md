
## DATABASES

We did many labs under this topic. I will share 2 labs i found interesting

## FIRST LAB :Build Your DB Server and Interact With Your DB Using an App
I worked through a hands-on lab with Amazon RDS, learning how to create a highly available database instance and connect it to a web server. Here's what I did.
# Task 1: Creating a Security Group for RDS
I navigated to the EC2 service and selected Security Groups from the left navigation pane. I created a new security group specifically to allow my web server to access the RDS database instance. I configured inbound rules to permit MySQL/Aurora traffic (port 3306) from the web server's security group, ensuring secure communication between the application tier and database tier. This security group would be applied when launching the RDS instance.
# Task 2: Creating a DB Subnet Group
I went to the RDS service and selected Subnet Groups from the left menu. I created a new DB subnet group, which tells RDS which subnets can be used for the database deployment. I selected subnets from at least two different Availability Zones to meet the Multi-AZ requirement, ensuring high availability and automatic failover capability for the database.
# Task 3: Launching a Multi-AZ RDS MySQL Instance
I navigated to the RDS Dashboard and clicked "Create database." I configured the following settings:

- Engine type: MySQL
- Deployment option: Multi-AZ DB instance for high availability
- DB instance identifier: Provided a unique name
- Master username and password: Set credentials for database access
- Instance specifications: Selected the appropriate instance class
- Storage: Configured storage type and allocated storage size
- VPC: Selected my VPC
- Subnet group: Chose the DB subnet group I created in Task 2
- Security group: Applied the security group from Task 1
- Availability Zone: Let AWS automatically select zones for the primary and standby instances

I then launched the database instance and waited for it to become available. The Multi-AZ deployment automatically created a standby replica in a different Availability Zone for failover protection.
# Task 4: Connecting the Web Application to the Database
Once the RDS instance was available, I copied the database endpoint address from the RDS console. I opened the web application running on my web server by navigating to its URL in a browser. I configured the application to connect to the database by entering:

- Database endpoint/hostname
- Database name
- Master username
- Password

I tested the connection to verify the web application could successfully communicate with the RDS database. I then interacted with the application, performing operations that read from and wrote to the database to confirm full functionality.


<img width="1600" height="900" alt="Screenshot (1364)" src="https://github.com/user-attachments/assets/754b8b98-8c7a-4b93-9286-e1e116ca44c5" />
<img width="1600" height="900" alt="Screenshot (1365)" src="https://github.com/user-attachments/assets/779c24e9-2b55-4d13-b206-4d33684a5cc6" />
<img width="1600" height="900" alt="Screenshot (1366)" src="https://github.com/user-attachments/assets/c9144049-c96a-46c5-93b4-98378f02f200" />
<img width="1600" height="900" alt="Screenshot (1369)" src="https://github.com/user-attachments/assets/9c3c4392-848f-48e9-af5a-cca1c4fade72" />
<img width="1600" height="900" alt="Screenshot (1370)" src="https://github.com/user-attachments/assets/07b4439d-4adb-45f2-98c5-68a574afc8de" />
<img width="1600" height="900" alt="Screenshot (1377)" src="https://github.com/user-attachments/assets/53996983-3a62-4edc-9025-c5f5215d1e0d" />
<img width="1600" height="900" alt="Screenshot (1378)" src="https://github.com/user-attachments/assets/6e3e76ac-7fc3-43f7-8d15-3343debcd595" />
<img width="1600" height="900" alt="Screenshot (1379)" src="https://github.com/user-attachments/assets/73fcfe5a-6e8e-4c98-942f-3006cfa210e1" />
<img width="1600" height="900" alt="Screenshot (1380)" src="https://github.com/user-attachments/assets/5a422f81-3abe-40bd-9723-aa4a950a2f93" />
<img width="1600" height="900" alt="Screenshot (1381)" src="https://github.com/user-attachments/assets/11a328a7-e443-4a58-8fc0-68f5294770d7" />

# CHALLENGES
I initially encountered a connection timeout error when the web application tried to access the database. After troubleshooting, I realized I had configured the security group inbound rule incorrectly—I had allowed traffic from a specific IP address instead of from the web server's security group. Once I updated the rule to reference the web server's security group as the source, the connection worked successfully.

# WHAT I LEARNED:
Here's what I learned from this lab:
- I launched an Amazon RDS database with high availability, which means it has backups and won't easily go down.
- I launched an Amazon RDS database with high availability, which means it has backups and won't easily go down.
- I opened up a web application and got it to read and write data to my database, seeing everything work together.
  # OVERALL
  I learned how to create a database on AWS and hook it up to a website so they can communicate with each other.

# Lab Complete 🎓

## SECOND LAB

## Chalenge Lab : Build And Access an RDS server

I worked through a hands-on lab with Amazon RDS, learning how to create a database instance, connect to it from a Linux server, create tables, insert data, and perform SQL queries. Here's what I did.
# Creating the RDS Database Instance
I navigated to the RDS service in the AWS Management Console and clicked "Create database." I configured the following settings:

- Engine: Selected either Aurora or MySQL
- Template: Chose Dev/Test or Free tier option
- DB instance class: Selected a small db.t3 instance (micro to medium size)
- Storage: Configured 100GB or less with gp2 storage type
-VPC: Selected the Lab VPC that was provided
- Security group: Configured the security group to allow inbound MySQL traffic (port 3306) from the LinuxServer
- Multi-AZ deployment: Did not create a standby instance to keep costs down

I launched the database and waited for it to become available, then copied the database endpoint address.
Connecting to the Linux Server
- I downloaded the PPK file from the lab credentials and noted the LinuxServer public IP address. I used PuTTY to SSH into the LinuxServer by configuring the hostname and selecting the PPK file for authentication.
Once connected, I installed the MySQL client on the server so I could connect to my RDS database from the command line.
Connecting to the RDS Database
I used the MySQL client to connect to my RDS instance using the endpoint address, master username, and password I had configured during database creation.
# Creating the RESTART Table
I created the first table called RESTART with four columns:

- Student ID (primary key)
- Student Name
- Restart City
- Graduation Date

I inserted 10 rows of sample student data into the table, then ran a SELECT statement to display all the records and verify the data was properly stored.
# Creating the CLOUD_PRACTITIONER Table
I created the second table called CLOUD_PRACTITIONER with two columns:

- Student ID (foreign key)
- Certification Date

I inserted 5 rows of sample certification data, then ran a SELECT statement to view all the records.
# Performing an INNER JOIN Query
Finally, I executed an INNER JOIN query between the RESTART and CLOUD_PRACTITIONER tables. The query joined on Student ID and displayed Student ID, Student Name, and Certification Date together, showing which students had earned their Cloud Practitioner certification.
I took screenshots at each step to document my work for the assignment submission.

<img width="1600" height="900" alt="Screenshot (1422)" src="https://github.com/user-attachments/assets/d0e73d9f-bae0-4fd1-b963-afe587621e67" />
<img width="653" height="410" alt="Screenshot (1427)" src="https://github.com/user-attachments/assets/f054c6bb-b94d-4778-82ac-8bf67a753611" />
<img width="662" height="444" alt="Screenshot (1430)" src="https://github.com/user-attachments/assets/765e7cb0-b794-4ff1-a7aa-1fe7cb78fbcb" />
<img width="665" height="428" alt="Screenshot (1429)" src="https://github.com/user-attachments/assets/ddf9a79a-6594-454c-bab6-dba8c8d3f7fa" />
<img width="661" height="434" alt="Screenshot (1431)" src="https://github.com/user-attachments/assets/c9fc0288-8d03-4843-9318-71be3183bd31" />
<img width="661" height="436" alt="Screenshot (1432)" src="https://github.com/user-attachments/assets/17505c00-ee5b-4b0c-9fe3-33f724b373dc" />
<img width="660" height="440" alt="Screenshot (1433)" src="https://github.com/user-attachments/assets/c5133a30-5300-469c-81b1-0529bb6e2992" />
<img width="656" height="428" alt="Screenshot (1434)" src="https://github.com/user-attachments/assets/a37a2a07-194c-414e-8ac3-a67ffda87b2c" />
<img width="666" height="442" alt="Screenshot (1435)" src="https://github.com/user-attachments/assets/e75b8650-73a7-4301-9298-057df586d394" />
<img width="665" height="425" alt="Screenshot (1436)" src="https://github.com/user-attachments/assets/5b4b96e9-53c9-40e2-9906-189911d22167" />
<img width="673" height="437" alt="Screenshot (1439)" src="https://github.com/user-attachments/assets/48edddac-0b9d-4190-8926-10f179c8d0fb" />

# CHALLENGES
I initially had trouble connecting to the RDS database from the LinuxServer. The connection kept timing out, and I realized I had forgotten to update the RDS security group's inbound rules to allow traffic from the LinuxServer's security group. Once I added the correct inbound rule allowing MySQL traffic (port 3306) from the LinuxServer's security group, the connection worked successfully.

## WHAT I LEARNED

Here's what I learned from this lab:
- I set up an RDS instance on AWS, which is a managed database that Amazon handles for me.
-  I used the RDS Query Editor to search and retrieve data from my database without needing any extra tools.

# OVERALL
 I learned how to create a database on AWS and start working with the data inside it right away using simple queries
  
            
## Lab Complete 🎓





  
