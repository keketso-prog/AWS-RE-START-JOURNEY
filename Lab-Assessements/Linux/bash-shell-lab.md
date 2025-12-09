# BASH SHELL SCRIPTING 

I worked through a hands-on lab creating a Bash script to automate folder backups on a Linux system, learning shell scripting, file permissions, and archive creation. Here's what I did.

# Task 1: Connecting to the EC2 Instance via SSH
- I started by accessing the lab credentials. I clicked the "Details" dropdown menu and selected "Show" to view the credentials window.
- I downloaded the labsuser.ppk file (saved to my Downloads directory) and noted the PublicIP address before closing the panel.
- I then opened PuTTY and configured the SSH connection by entering the PublicIP address in the Host Name field.
- I navigated to Connection > SSH > Auth in the left menu, browsed and selected the downloaded labsuser.ppk file for authentication, and clicked "Open" to establish the SSH connection to the EC2 instance.

<img width="444" height="437" alt="Screenshot (1879)" src="https://github.com/user-attachments/assets/7017b527-ea44-42a2-9bca-b22605249755" />


# Task 2: Writing the Backup Shell Script

Once connected, I validated my location by typing pwd to confirm I was in the home directory.
- Creating the Script File:
I created a new shell script file called backup.sh using the touch command.


<img width="667" height="424" alt="Screenshot (1358)" src="https://github.com/user-attachments/assets/ebded883-5bc5-4f0a-9120-9f227eed0ac1" />
<img width="673" height="422" alt="Screenshot (1359)" src="https://github.com/user-attachments/assets/6f2d6385-9e17-421a-a941-f07a472e523e" />

- Setting File Permissions:
I made the script executable by changing the file privileges using chmod to add execute permissions.
- Editing the Script:
I opened the backup.sh file using my preferred text editor (nano). I activated insert mode to begin writing the script.
- Creating Variables:
I created a variable to capture the current date in YYYY-MM-DD format. Then I created another variable for the daily backup filename, combining the date with "-backup-companyA.tar.gz".
- Adding the Backup Command:
I added a tar command to compress the CompanyA folder into a gzip archive and save it in the backups folder with the dated filename.
- Saving and Exiting:
I saved my script and exited from the editor by pressing the appropriate key combinations.
- Running the Script:
I executed the backup.sh script to perform the backup operation.
- Verifying the Backup:
I confirmed the archive was created successfully by listing the contents of the backups folder. This displayed the newly created archive file named with today's date (for example, 2025-12-05-backup-companyA.tar.gz).

<img width="494" height="441" alt="Screenshot (1360)" src="https://github.com/user-attachments/assets/3558291e-ce78-48c0-a106-af69af7e78b9" />
<img width="494" height="441" alt="Screenshot (1360)" src="https://github.com/user-attachments/assets/1ce87ab2-b5ce-4945-b901-fff3e3af2bc6" />
<img width="490" height="415" alt="Screenshot (1361)" src="https://github.com/user-attachments/assets/df4f8a17-9bae-4628-8a29-5d9f5c10d606" />
<img width="570" height="421" alt="Screenshot (1362)" src="https://github.com/user-attachments/assets/8c8667e9-dca6-4d7a-a17b-7531533765c0" />
<img width="570" height="409" alt="Screenshot (1363)" src="https://github.com/user-attachments/assets/eae43c71-bc04-44f6-8d14-c6d64b9ce5a2" />

# CHALLENGES
I initially forgot to create the backups directory before running the script, which caused the tar command to fail with a "No such file or directory" error. I had to create the directory using mkdir backups before running the script again, which taught me the importance of verifying all required directories exist before executing file operations.

# WHAT I LEARNED
Here's what I learned from this lab:
-  I wrote a bash script that automatically backs up a folder, so I don't have to manually copy files every time
  # OVERALL
   I learned how to automate repetitive backup tasks using simple scripting instead of doing it by hand

# Lab Complete 🎓

