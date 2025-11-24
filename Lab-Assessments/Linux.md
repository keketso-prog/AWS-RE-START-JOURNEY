## LINUX

 We did many labs under this topic, i will share two from this topic that i found interesting. The first is the Bash Shell Scripting and the second is the Challenge we were given to yield a certain outcome.

#  BASH SHELL SCRIPTING 

  Objectives
In this lab, you will:

Create a bash script that will automate the backup of a folder.

# TASK 1

Firstly i have to follow this instructions to connect using SSH:

Select the Details drop-down menu above these instructions you are currently reading, and then select Show. A Credentials window will be presented.

Select the Download PPK button and save the labsuser.ppk file.
Typically your browser will save it to the Downloads directory.

Make a note of the PublicIP address.

Then exit the Details panel by selecting the X.

Download  PuTTY to SSH into the Amazon EC2 instance. If you do not have PuTTY installed on your computer, download it here.

Open putty.exe

# TASK 2

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

# WHAT I LEARNED
Here's what I learned from this lab:
-  I wrote a bash script that automatically backs up a folder, so I don't have to manually copy files every time
  # OVERALL
   I learned how to automate repetitive backup tasks using simple scripting instead of doing it by hand

# Lab Complete 🎓

## SECOND LAB

# BASH SHELL SCRIPTING EXERCISE

 Objectives
In this challenge, you will:

Create a directory

# TASK 1

Firstly i have to follow this instructions to connect using SSH:

Select the Details drop-down menu above these instructions you are currently reading, and then select Show. A Credentials window will be presented.

Select the Download PPK button and save the labsuser.ppk file.
Typically your browser will save it to the Downloads directory.

Make a note of the PublicIP address.

Then exit the Details panel by selecting the X.

Download  PuTTY to SSH into the Amazon EC2 instance. If you do not have PuTTY installed on your computer, download it here.

Open putty.exe

# TASK 2

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

#  WHAT I LEARNED
Here's what I learned from this task:
-  I learned how to use a for loop in bash to repeat actions multiple times instead of typing the same command 25 times.
-   figured out how to automatically search for files that already exist and find the highest number, so the script knows where to continue from
-    I learned how to do calculations in a script, like taking the last number and adding 1 to it, or adding 24 to get the ending number
-    I used ls -lh to check that all my files were created correctly with the right names and in the right order.
-    he biggest lesson was understanding how to make a script smart enough to figure things out on its own instead of me having to tell it the numbers every time.

 # OVERALL
I learned how to write a script that's actually intelligent and can adapt based on what's already there, not just blindly follow hard-coded instructions

##  Lab Complete 🎓
