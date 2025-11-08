INSTRUCTIONS on how to follow labs by week

👉❗ = New Lab

👉❗  LAB ASSESSMENTS : EC2

Had to make a lab that introduced me to Amazon EC2. 💻
After doing the lab, the outcome was to learn the following
Launch a web server with termination protection enabled

- Monitor Your EC2 instance

- Modify the security group that your web server is using to allow HTTP access

- Resize your Amazon EC2 instance to scale

- Test termination protection

- Terminate your EC2 instance

  I had to start the lab
  Launch the instance on the EC2
   <img width="1600" height="900" alt="Screenshot (1296)" src="https://github.com/user-attachments/assets/0d33d8d5-73b5-44bb-b691-9ea7cdfdccf2" />

  TASK 1 :
  LAUNCH EC2 INSTANCE
  
  Under task one i had to follow this steps below to get tHe required outcome

-  Name the instance
-  Choose an Amazon machine image
-  Choose an instance type
-  Configure a key pair
-  Configure the network settings
-  Add storage
-  Configure advanced network settings
-  Then finally launch the instance
  <img width="1600" height="900" alt="Screenshot (1289)" src="https://github.com/user-attachments/assets/ee7a4d40-d86f-4b4f-b547-aec3bead5cda" />
   

  TASK 2 :
  MONITOR THE INSTANCE
  
  under task two, i had to do the following
  - Monitor and troubleshoot to get the this outcome
    THIS IS THE OUTCOME
    <img width="1600" height="900" alt="Screenshot (1290)" src="https://github.com/user-attachments/assets/869d8dd6-32c1-4142-91b3-e084294f481a" />


    TASK 3 :
    UPDATE SECURITY RULES AND ACCESS THE WEB SERVER
    
    Under task three i had to do the following
    - Go to network & security
    - The select security groups
    - select inbound rules
    - Edit the rules with the following : - Type: HTTP      Source: Anywhere-IPv4
    - Save the rules and reload web server to see the desired outcome.
      THIS IS THE OUTCOME
      <img width="1600" height="900" alt="Screenshot (1291)" src="https://github.com/user-attachments/assets/be1cbd61-ffbd-471c-b49c-f251c5d534fa" />
      <img width="1600" height="900" alt="Screenshot (1292)" src="https://github.com/user-attachments/assets/aafe013c-5816-45d1-af45-6270afcd694a" />

      
   
    TASK 4 :
    RESIZE YOUR INSTANCE
    
    Under task four i had to do the following
    - Navigate to instance and select the web server you created
    - Select instance state > Stop instance
    - Instance must display stopped
    - Change the instance to t3.small under Actions tab
    - Resize volume under actions to 10
    The desired outcome must display the new changes i just did
     THIS IS THE OUTCOME
<img width="1600" height="900" alt="Screenshot (1293)" src="https://github.com/user-attachments/assets/03ce1736-f693-44da-91b6-9242d756dfd4" />



TASK 5:
TEST TERMINATION PROCESS

Under task five i had to do the following
- Navigate to instance, and then select the web server you just created
- Under instance menu select the termination delete tab
- Bescause he it did not work, go to actions > select instance setting > change protection then uncheck ENABLE
- Go to actions again instance state > terminate instance
  THIS IS THE OUTCOME
  <img width="1600" height="900" alt="Screenshot (1294)" src="https://github.com/user-attachments/assets/429b93a7-4133-45b8-b5ec-a05ce8ecb84d" />

  <img width="1600" height="900" alt="Screenshot (1295)" src="https://github.com/user-attachments/assets/7c524d9c-3e11-4367-b1a0-5da26498799b" />


  Lab Complete 🎓

 👉❗  LAB ASSESSEMENT : LINUX

   Week 2 was focused on linux. We did many labs under this topic, i will share two from this topic that i found interesting. The first is the Bash Shell Scripting and the second is the Challenge we were given to yield a certain outcome.

  BASH SHELL SCRIPTING 💻

  Objectives
In this lab, you will:

Create a bash script that will automate the backup of a folder.

TASK 1

Firstly i have to follow this instructions to connect using SSH:

Select the Details drop-down menu above these instructions you are currently reading, and then select Show. A Credentials window will be presented.

Select the Download PPK button and save the labsuser.ppk file.
Typically your browser will save it to the Downloads directory.

Make a note of the PublicIP address.

Then exit the Details panel by selecting the X.

Download  PuTTY to SSH into the Amazon EC2 instance. If you do not have PuTTY installed on your computer, download it here.

Open putty.exe

TASK 2

Write a shell script

I need to create a Bash shell script that automatically backs up the CompanyA folder by compressing it into an archive file. I'll name the archive using today's date followed by "-backup-companyA.tar.gz"

STEPS TAKEN

-Validate that im in the home folder by typing pwd

outcome is a s follows  :  

<img width="667" height="424" alt="Screenshot (1358)" src="https://github.com/user-attachments/assets/ebded883-5bc5-4f0a-9120-9f227eed0ac1" />


create a generic shell script called backup.sh

<img width="673" height="422" alt="Screenshot (1359)" src="https://github.com/user-attachments/assets/6f2d6385-9e17-421a-a941-f07a472e523e" />


change the file privileges to make backup.sh

<img width="494" height="441" alt="Screenshot (1360)" src="https://github.com/user-attachments/assets/3558291e-ce78-48c0-a106-af69af7e78b9" />


use my preferred text editor to open the backup.sh file for editing

To activate insert mode

create a variable for the current date

<img width="494" height="441" alt="Screenshot (1360)" src="https://github.com/user-attachments/assets/1ce87ab2-b5ce-4945-b901-fff3e3af2bc6" />


create a variable for the backup file for the day

saved my script and exit from the editor

<img width="490" height="415" alt="Screenshot (1361)" src="https://github.com/user-attachments/assets/df4f8a17-9bae-4628-8a29-5d9f5c10d606" />


 run backup.sh

<img width="570" height="421" alt="Screenshot (1362)" src="https://github.com/user-attachments/assets/8c8667e9-dca6-4d7a-a17b-7531533765c0" />


 verify that the archive is created in the backups folder

 <img width="570" height="409" alt="Screenshot (1363)" src="https://github.com/user-attachments/assets/eae43c71-bc04-44f6-8d14-c6d64b9ce5a2" />


 Lab Complete 🎓

👉❗ CHALLENGE LAB : BASH SHELL SCRIPTING EXERCISE

 Objectives
In this challenge, you will:

Create a directory

TASK 1

Firstly i have to follow this instructions to connect using SSH:

Select the Details drop-down menu above these instructions you are currently reading, and then select Show. A Credentials window will be presented.

Select the Download PPK button and save the labsuser.ppk file.
Typically your browser will save it to the Downloads directory.

Make a note of the PublicIP address.

Then exit the Details panel by selecting the X.

Download  PuTTY to SSH into the Amazon EC2 instance. If you do not have PuTTY installed on your computer, download it here.

Open putty.exe

TASK 2

MY CHALLENGE INSTRUCTIONS :

Write a Bash script based on the following requirements:

Creates 25 empty (0 KB) files. (Hint: Use the touch command.)
The file names should be <yourName><number>, <yourName><number+1>, <yourName><number+2>, and so on.
Design the script so that each time you run it, it creates the next batch of 25 files with increasing numbers starting with the last or maximum number that already exists.
Do not hard code these numbers. You need to generate them by using automation.
Test the script. Display a long list of the directory and its contents to validate that the script created the expected files.

HERE is steps i took to achieve this

Step 1: I Create the script file

<img width="656" height="418" alt="Screenshot (1342)" src="https://github.com/user-attachments/assets/3583b920-2f9f-4671-85bb-a58a35c9a622" />

<img width="1033" height="425" alt="Screenshot (1343)" src="https://github.com/user-attachments/assets/c27bbd65-8a94-4243-9dc3-a10514918980" />


Step 2: I wrote the script

<img width="1044" height="427" alt="Screenshot (1347)" src="https://github.com/user-attachments/assets/c1196432-7b2c-4765-b44a-f32fa98576ef" />

<img width="1052" height="440" alt="Screenshot (1348)" src="https://github.com/user-attachments/assets/c65db1c5-c38a-4ad2-a84a-1e4c5f8ae859" />


Step 3:  I replace "yourName"

<img width="1049" height="436" alt="Screenshot (1351)" src="https://github.com/user-attachments/assets/786985c6-f0ac-4178-9469-0cd777e1c6cc" />

Step 4: I saved and exited

<img width="1069" height="425" alt="Screenshot (1352)" src="https://github.com/user-attachments/assets/21da6311-601a-4d9e-a08b-8e9ec5cf9cf0" />

Step 5: I made sure it is executable

<img width="1046" height="447" alt="Screenshot (1353)" src="https://github.com/user-attachments/assets/a5f8775a-d9d3-4e98-ab3b-1c8f1556c9c5" />


Step 6: I ran the script

<img width="1070" height="457" alt="Screenshot (1354)" src="https://github.com/user-attachments/assets/5e2f6910-1f7a-446f-8a13-6a55dea68936" />

Step 7: I Verified the files

<img width="1600" height="900" alt="Screenshot (1355)" src="https://github.com/user-attachments/assets/09a7079d-34d0-4fca-b681-cba546136524" />

Step 8: I tested it again (run the script multiple times)

<img width="1600" height="900" alt="Screenshot (1356)" src="https://github.com/user-attachments/assets/3dff70ff-bd06-4695-b17e-67fff30d63c9" />

<img width="1600" height="900" alt="Screenshot (1357)" src="https://github.com/user-attachments/assets/042eeca0-c2e9-4256-9e8e-430d96baf18e" />


Each time i ran it, it created the next 25 files with increasing numbers!




 

  Lab Complete 🎓

  👉❗ Lab Assessment : DATABASES

  Launch an Amazon RDS DB instance with high availability.

Configure the DB instance to permit connections from your web server.

Open a web application and interact with your database.

TASK 1

create a security group to allow your web server to access your RDS DB instance. The security group will be used when you launch the database instance

TASK 2

create a DB subnet group that is used to tell RDS which subnets can be used for the database. Each DB subnet group requires subnets in at least two Availability Zones.

TASK 3

configure and launch a Multi-AZ Amazon RDS for MySQL database instance.

TASK 4

open a web application running on my web server and configure it to use the database

Lab Complete 🎓

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




  
  
