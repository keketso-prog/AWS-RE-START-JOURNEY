
## DATABASES

We did many labs under this topic. I will share two labs i found interesting

## FIRST LAB :Build Your DB Server and Interact With Your DB Using an App

Launch an Amazon RDS DB instance with high availability.

Configure the DB instance to permit connections from your web server.

Open a web application and interact with your database.

# TASK 1

create a security group to allow your web server to access your RDS DB instance. The security group will be used when you launch the database instance

<img width="1600" height="900" alt="Screenshot (1364)" src="https://github.com/user-attachments/assets/754b8b98-8c7a-4b93-9286-e1e116ca44c5" />

<img width="1600" height="900" alt="Screenshot (1365)" src="https://github.com/user-attachments/assets/779c24e9-2b55-4d13-b206-4d33684a5cc6" />


# TASK 2

create a DB subnet group that is used to tell RDS which subnets can be used for the database. Each DB subnet group requires subnets in at least two Availability Zones.

<img width="1600" height="900" alt="Screenshot (1366)" src="https://github.com/user-attachments/assets/c9144049-c96a-46c5-93b4-98378f02f200" />

<img width="1600" height="900" alt="Screenshot (1367)" src="https://github.com/user-attachments/assets/b6f1aaf4-d856-4855-bf9f-f17b662c295f" />

<img width="1600" height="900" alt="Screenshot (1368)" src="https://github.com/user-attachments/assets/8d3856b4-0acf-478c-82bf-d8519e95e13e" />

<img width="1600" height="900" alt="Screenshot (1369)" src="https://github.com/user-attachments/assets/9c3c4392-848f-48e9-af5a-cca1c4fade72" />

# TASK 3

configure and launch a Multi-AZ Amazon RDS for MySQL database instance.

<img width="1600" height="900" alt="Screenshot (1370)" src="https://github.com/user-attachments/assets/07b4439d-4adb-45f2-98c5-68a574afc8de" />

<img width="1600" height="900" alt="Screenshot (1371)" src="https://github.com/user-attachments/assets/3ee49533-3a86-46c9-979c-dee8ef9375e3" />

<img width="1600" height="900" alt="Screenshot (1372)" src="https://github.com/user-attachments/assets/10ffc0ed-4904-41de-be21-7bd8b72f68d5" />

<img width="1600" height="900" alt="Screenshot (1373)" src="https://github.com/user-attachments/assets/f9259279-6450-459a-b8c6-e80645e62666" />

<img width="1600" height="900" alt="Screenshot (1374)" src="https://github.com/user-attachments/assets/9cf63688-b30b-4883-a87b-0b0f7e881531" />

<img width="1600" height="900" alt="Screenshot (1375)" src="https://github.com/user-attachments/assets/45da691e-799a-4cf7-b24a-32aba3b8ae3b" />

<img width="1600" height="900" alt="Screenshot (1377)" src="https://github.com/user-attachments/assets/53996983-3a62-4edc-9025-c5f5215d1e0d" />

# TASK 4

open a web application running on my web server and configure it to use the database

<img width="1600" height="900" alt="Screenshot (1378)" src="https://github.com/user-attachments/assets/6e3e76ac-7fc3-43f7-8d15-3343debcd595" />

<img width="1600" height="900" alt="Screenshot (1379)" src="https://github.com/user-attachments/assets/73fcfe5a-6e8e-4c98-942f-3006cfa210e1" />

<img width="1600" height="900" alt="Screenshot (1380)" src="https://github.com/user-attachments/assets/5a422f81-3abe-40bd-9723-aa4a950a2f93" />

<img width="1600" height="900" alt="Screenshot (1381)" src="https://github.com/user-attachments/assets/11a328a7-e443-4a58-8fc0-68f5294770d7" />

# WHAT I LEARNED:
Here's what I learned from this lab:
- I launched an Amazon RDS database with high availability, which means it has backups and won't easily go down.
- I launched an Amazon RDS database with high availability, which means it has backups and won't easily go down.
- I opened up a web application and got it to read and write data to my database, seeing everything work together.
  # OVERALL
  I learned how to create a database on AWS and hook it up to a website so they can communicate with each other.

# Lab Complete 🎓

SECOND LAB

👉❗ Chalenge Lab : Build And Access an RDS server

Create an RDS instance
Use the Amazon RDS Query Editor to query data

To finish the Challenge do the following:

How I Did This Lab
What I Did with RDS
I created an Amazon RDS database using either Aurora or MySQL. I had to follow these rules:

Picked Dev/Test or Free tier
Used a small db.t3 instance (micro to medium size)
Set up 100GB storage or less (gp2 type)
Used the Lab VPC that was given
Made sure the security group lets the LinuxServer connect to my database
Did not create a standby instance

<img width="1600" height="900" alt="Screenshot (1422)" src="https://github.com/user-attachments/assets/d0e73d9f-bae0-4fd1-b963-afe587621e67" />

<img width="653" height="410" alt="Screenshot (1427)" src="https://github.com/user-attachments/assets/f054c6bb-b94d-4778-82ac-8bf67a753611" />


Connecting to the Server
I downloaded the PPK file (for Windows) from the lab. Then I wrote down the LinuxServer address and used SSH to connect to it. After connecting, I installed MySQL client on the server so I could connect to my RDS database.
Creating Tables and Adding Data
I made two tables in my database:
First table - RESTART:

<img width="662" height="444" alt="Screenshot (1430)" src="https://github.com/user-attachments/assets/765e7cb0-b794-4ff1-a7aa-1fe7cb78fbcb" />
<img width="665" height="428" alt="Screenshot (1429)" src="https://github.com/user-attachments/assets/ddf9a79a-6594-454c-bab6-dba8c8d3f7fa" />


Has 4 columns: Student ID, Student Name, Restart City, and Graduation Date
I added 10 rows of sample data
I ran SELECT to show all the data

<img width="661" height="434" alt="Screenshot (1431)" src="https://github.com/user-attachments/assets/c9fc0288-8d03-4843-9318-71be3183bd31" />
<img width="661" height="436" alt="Screenshot (1432)" src="https://github.com/user-attachments/assets/17505c00-ee5b-4b0c-9fe3-33f724b373dc" />
<img width="660" height="440" alt="Screenshot (1433)" src="https://github.com/user-attachments/assets/c5133a30-5300-469c-81b1-0529bb6e2992" />


Second table - CLOUD_PRACTITIONER:

Has 2 columns: Student ID and Certification Date
I added 5 rows of sample data
I ran SELECT to show all the data

<img width="656" height="428" alt="Screenshot (1434)" src="https://github.com/user-attachments/assets/a37a2a07-194c-414e-8ac3-a67ffda87b2c" />
<img width="666" height="442" alt="Screenshot (1435)" src="https://github.com/user-attachments/assets/e75b8650-73a7-4301-9298-057df586d394" />
<img width="665" height="425" alt="Screenshot (1436)" src="https://github.com/user-attachments/assets/5b4b96e9-53c9-40e2-9906-189911d22167" />



Joining the Tables
Finally, I did an INNER JOIN between my two tables to show Student ID, Student Name, and Certification Date together.
I took screenshots of each step to submit for the assignment

<img width="673" height="437" alt="Screenshot (1439)" src="https://github.com/user-attachments/assets/48edddac-0b9d-4190-8926-10f179c8d0fb" />








  
            
Lab Complete 🎓




  
