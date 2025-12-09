# BASH SHELL SCRIPTING EXERCISE

 I worked through a hands-on lab creating a Bash script that automatically generates batches of files with incrementing numbers, learning about automation, loops, and dynamic file creation. Here's what I did.
# Task 1: Connecting to the EC2 Instance via SSH
I started by accessing the lab credentials. I clicked the "Details" dropdown menu and selected "Show" to view the credentials window. I downloaded the labsuser.ppk file (saved to my Downloads directory) and noted the PublicIP address before closing the panel.
I then opened PuTTY and configured the SSH connection by entering the PublicIP address in the Host Name field. I navigated to Connection > SSH > Auth in the left menu, browsed and selected the downloaded labsuser.ppk file for authentication, and clicked "Open" to establish the SSH connection to the EC2 instance.
# Task 2: Writing the Automated File Creation Script
My challenge was to create a Bash script that generates 25 empty files at a time, with filenames that increment automatically based on the highest existing number, without any hard-coded values.
- Step 1: Creating the Script File
I created a new Bash script file in my home directory to hold the automation logic.
- Step 2: Writing the Script Logic
- I wrote a script that:

Searched for existing files matching my naming pattern to find the maximum number already used
Calculated the starting number for the next batch (maximum number + 1, or 1 if no files existed)
Used a loop to create 25 empty files using the touch command
Incremented the number for each file created within the batch

- Step 3: Personalizing the Filename
I replaced "yourName" in the script with my actual name to create personalized filenames like myName1, myName2, myName3, and so on.
- Step 4: Saving and Exiting
I saved the script and exited the text editor.
- Step 5: Making the Script Executable
I changed the file permissions to make the script executable so it could be run directly.
- Step 6: Running the Script
I executed the script for the first time, which created files numbered 1 through 25.
- Step 7: Verifying the Files
I displayed a long list of the directory contents to confirm all 25 files were created with the correct naming pattern and 0 KB file size.
- Step 8: Testing Multiple Runs
I ran the script multiple times to verify the automation worked correctly. Each execution created the next batch of 25 files with properly incrementing numbers—files 26-50 on the second run, 51-75 on the third run, and so on.




<img width="656" height="418" alt="Screenshot (1342)" src="https://github.com/user-attachments/assets/3583b920-2f9f-4671-85bb-a58a35c9a622" />
<img width="1033" height="425" alt="Screenshot (1343)" src="https://github.com/user-attachments/assets/c27bbd65-8a94-4243-9dc3-a10514918980" />
<img width="1044" height="427" alt="Screenshot (1347)" src="https://github.com/user-attachments/assets/c1196432-7b2c-4765-b44a-f32fa98576ef" />
<img width="1052" height="440" alt="Screenshot (1348)" src="https://github.com/user-attachments/assets/c65db1c5-c38a-4ad2-a84a-1e4c5f8ae859" />
<img width="1049" height="436" alt="Screenshot (1351)" src="https://github.com/user-attachments/assets/786985c6-f0ac-4178-9469-0cd777e1c6cc" />
<img width="1069" height="425" alt="Screenshot (1352)" src="https://github.com/user-attachments/assets/21da6311-601a-4d9e-a08b-8e9ec5cf9cf0" />
<img width="1046" height="447" alt="Screenshot (1353)" src="https://github.com/user-attachments/assets/a5f8775a-d9d3-4e98-ab3b-1c8f1556c9c5" />
<img width="1070" height="457" alt="Screenshot (1354)" src="https://github.com/user-attachments/assets/5e2f6910-1f7a-446f-8a13-6a55dea68936" />
<img width="1600" height="900" alt="Screenshot (1355)" src="https://github.com/user-attachments/assets/09a7079d-34d0-4fca-b681-cba546136524" />
<img width="1600" height="900" alt="Screenshot (1356)" src="https://github.com/user-attachments/assets/3dff70ff-bd06-4695-b17e-67fff30d63c9" />
<img width="1600" height="900" alt="Screenshot (1357)" src="https://github.com/user-attachments/assets/042eeca0-c2e9-4256-9e8e-430d96baf18e" />

# CHALLENGES
I initially struggled with dynamically finding the maximum file number without hard-coding values. My first attempt used a simple approach that didn't properly handle the case when no files existed yet, causing the script to fail on the first run. I had to add conditional logic to check if any matching files existed and set the starting number to 1 if the directory was empty, or to the maximum number plus 1 if files already existed


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

