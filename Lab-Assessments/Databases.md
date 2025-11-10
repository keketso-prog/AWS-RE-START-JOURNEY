👉❗ Lab Assessment : DATABASES

We did many labs under this topic. I will share two labs i found interesting

FIRST LAB

Launch an Amazon RDS DB instance with high availability.

Configure the DB instance to permit connections from your web server.

Open a web application and interact with your database.

TASK 1

create a security group to allow your web server to access your RDS DB instance. The security group will be used when you launch the database instance

<img width="1600" height="900" alt="Screenshot (1364)" src="https://github.com/user-attachments/assets/754b8b98-8c7a-4b93-9286-e1e116ca44c5" />

<img width="1600" height="900" alt="Screenshot (1365)" src="https://github.com/user-attachments/assets/779c24e9-2b55-4d13-b206-4d33684a5cc6" />


TASK 2

create a DB subnet group that is used to tell RDS which subnets can be used for the database. Each DB subnet group requires subnets in at least two Availability Zones.

<img width="1600" height="900" alt="Screenshot (1366)" src="https://github.com/user-attachments/assets/c9144049-c96a-46c5-93b4-98378f02f200" />

<img width="1600" height="900" alt="Screenshot (1367)" src="https://github.com/user-attachments/assets/b6f1aaf4-d856-4855-bf9f-f17b662c295f" />

<img width="1600" height="900" alt="Screenshot (1368)" src="https://github.com/user-attachments/assets/8d3856b4-0acf-478c-82bf-d8519e95e13e" />

<img width="1600" height="900" alt="Screenshot (1369)" src="https://github.com/user-attachments/assets/9c3c4392-848f-48e9-af5a-cca1c4fade72" />

TASK 3

configure and launch a Multi-AZ Amazon RDS for MySQL database instance.

<img width="1600" height="900" alt="Screenshot (1370)" src="https://github.com/user-attachments/assets/07b4439d-4adb-45f2-98c5-68a574afc8de" />

<img width="1600" height="900" alt="Screenshot (1371)" src="https://github.com/user-attachments/assets/3ee49533-3a86-46c9-979c-dee8ef9375e3" />

<img width="1600" height="900" alt="Screenshot (1372)" src="https://github.com/user-attachments/assets/10ffc0ed-4904-41de-be21-7bd8b72f68d5" />

<img width="1600" height="900" alt="Screenshot (1373)" src="https://github.com/user-attachments/assets/f9259279-6450-459a-b8c6-e80645e62666" />

<img width="1600" height="900" alt="Screenshot (1374)" src="https://github.com/user-attachments/assets/9cf63688-b30b-4883-a87b-0b0f7e881531" />

<img width="1600" height="900" alt="Screenshot (1375)" src="https://github.com/user-attachments/assets/45da691e-799a-4cf7-b24a-32aba3b8ae3b" />

<img width="1600" height="900" alt="Screenshot (1377)" src="https://github.com/user-attachments/assets/53996983-3a62-4edc-9025-c5f5215d1e0d" />

TASK 4

open a web application running on my web server and configure it to use the database

<img width="1600" height="900" alt="Screenshot (1378)" src="https://github.com/user-attachments/assets/6e3e76ac-7fc3-43f7-8d15-3343debcd595" />

<img width="1600" height="900" alt="Screenshot (1379)" src="https://github.com/user-attachments/assets/73fcfe5a-6e8e-4c98-942f-3006cfa210e1" />

<img width="1600" height="900" alt="Screenshot (1380)" src="https://github.com/user-attachments/assets/5a422f81-3abe-40bd-9723-aa4a950a2f93" />

<img width="1600" height="900" alt="Screenshot (1381)" src="https://github.com/user-attachments/assets/11a328a7-e443-4a58-8fc0-68f5294770d7" />


Lab Complete 🎓

SECOND LAB

👉❗ Chalenge Lab : Build And Access an RDS server

Create an RDS instance
Use the Amazon RDS Query Editor to query data

To finish the Challenge do the following:

Launch an Amazon RDS DB instance using either Amazon Aurora Provisioned DB or MySQL database engines. Make a note of the DB credentials, as it will be needed in next steps. Please note the following lab restrictions:

DatabaseEngine: Supported engines are Amazon Aurora or MySQL. Amazon Aurora serverless is not available.
Template: Choose Dev/Test or Free tier.
Availability and durability: Avoid creating a standby instance.
DB instance size: Choose Burstable classes - db.t3 instances of type db. t*.micro to db.t*.medium.
Storage: Choose General Purpose SSD (gp2) of a size up to 100 GB. Provisioned IOPS access is restricted.
Amazon VPC: Use the Lab VPC
Security Group: Include a security group that will allow the LinuxServer to connect to the RDS instance.
For MySQL, under Additional configuration - Enable Enhanced monitoring - Disable the option
Purchasing Options: On-Demand instances are allowed. Other purchasing options are disabled






  
            
Lab Complete 🎓




  
