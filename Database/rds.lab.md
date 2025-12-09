Build Your DB Server and Interact With Your DB Using an App
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
