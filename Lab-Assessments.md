INSTRUCTIONS on how to follow labs by week

👉❗ = New week

👉❗ WEEK 1 LAB ASSESSMENTS

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

 👉❗ WEEK 2 LAB ASSESSEMENT

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

create a generic shell script called backup.sh

change the file privileges to make backup.sh

use my preferred text editor to open the backup.sh file for editing

To activate insert mode

create a variable for the current date

create a variable for the backup file for the day

saved my script and exit from the editor

 run backup.sh

 verify that the archive is created in the backups folder

 Lab Complete 🎓

 CHALLENGE LAB : BASH SHELL SCRIPTING EXERCISE

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

Step 2: I wrote the script

Step 3:  I replace "yourName"

Step 4: I saved and exited

Step 5: I made sure it is executable

Step 6: I ran the script

Step 7: I Verified the files

Step 8: I tested it again (run the script multiple times)

Each time i ran it, it created the next 25 files with increasing numbers!




 

  Lab Complete 🎓
            



  
  
