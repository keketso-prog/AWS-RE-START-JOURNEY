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

# I launched the database and waited for it to become available, then copied the database endpoint address.

<img width="1600" height="900" alt="Screenshot (1422)" src="https://github.com/user-attachments/assets/d0e73d9f-bae0-4fd1-b963-afe587621e67" />

# Connecting to the Linux Server
- I downloaded the PPK file from the lab credentials and noted the LinuxServer public IP address. I used PuTTY to SSH into the LinuxServer by configuring the hostname and selecting the PPK file for authentication.
Once connected, I installed the MySQL client on the server so I could connect to my RDS database from the command line.
Connecting to the RDS Database
I used the MySQL client to connect to my RDS instance using the endpoint address, master username, and password I had configured during database creation.

<img width="653" height="410" alt="Screenshot (1427)" src="https://github.com/user-attachments/assets/f054c6bb-b94d-4778-82ac-8bf67a753611" />
<img width="662" height="444" alt="Screenshot (1430)" src="https://github.com/user-attachments/assets/765e7cb0-b794-4ff1-a7aa-1fe7cb78fbcb" />
<img width="665" height="428" alt="Screenshot (1429)" src="https://github.com/user-attachments/assets/ddf9a79a-6594-454c-bab6-dba8c8d3f7fa" />


# Creating the RESTART Table

I created the first table called RESTART with four columns:

- Student ID (primary key)
- Student Name
- Restart City
- Graduation Date

I inserted 10 rows of sample student data into the table, then ran a SELECT statement to display all the records and verify the data was properly stored.

<img width="661" height="434" alt="Screenshot (1431)" src="https://github.com/user-attachments/assets/c9fc0288-8d03-4843-9318-71be3183bd31" />
<img width="661" height="436" alt="Screenshot (1432)" src="https://github.com/user-attachments/assets/17505c00-ee5b-4b0c-9fe3-33f724b373dc" />
<img width="660" height="440" alt="Screenshot (1433)" src="https://github.com/user-attachments/assets/c5133a30-5300-469c-81b1-0529bb6e2992" />
<img width="656" height="428" alt="Screenshot (1434)" src="https://github.com/user-attachments/assets/a37a2a07-194c-414e-8ac3-a67ffda87b2c" />

# Creating the CLOUD_PRACTITIONER Table

I created the second table called CLOUD_PRACTITIONER with two columns:

- Student ID (foreign key)
- Certification Date

I inserted 5 rows of sample certification data, then ran a SELECT statement to view all the records.

<img width="666" height="442" alt="Screenshot (1435)" src="https://github.com/user-attachments/assets/e75b8650-73a7-4301-9298-057df586d394" />
<img width="665" height="425" alt="Screenshot (1436)" src="https://github.com/user-attachments/assets/5b4b96e9-53c9-40e2-9906-189911d22167" />

# Performing an INNER JOIN Query

Finally, I executed an INNER JOIN query between the RESTART and CLOUD_PRACTITIONER tables. The query joined on Student ID and displayed Student ID, Student Name, and Certification Date together, showing which students had earned their Cloud Practitioner certification.
I took screenshots at each step to document my work for the assignment submission.

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
