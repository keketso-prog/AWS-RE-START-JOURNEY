##   COMPUTE

## LAB ASSESSMENT : EC2

I had to make a lab that introduced me to Amazon EC2. 💻
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

 # TASK 1 :
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
   

 # TASK 2 :
  MONITOR THE INSTANCE
  
  under task two, i had to do the following
  - Monitor and troubleshoot to get the this outcome
    THIS IS THE OUTCOME
    <img width="1600" height="900" alt="Screenshot (1290)" src="https://github.com/user-attachments/assets/869d8dd6-32c1-4142-91b3-e084294f481a" />


 # TASK 3 :
UPDATE SECURITY RULES AND ACCESS THE WEB SERVER
    
 Under task three i had to do the following
 - Go to network & security
 - The select security groups
 - select inbound rules
 - Edit the rules with the following : - Type: HTTP      Source: Anywhere-IPv4
 - Save the rules and reload web server to see the desired outcome.
      THIS IS THE OUTCOME
      
  <img width="1600" height="900" alt="Screenshot (1291)" src="https://github.com/user-attachments/assets/64b7336e-63ba-46eb-82ab-e92095e1cf8a" />

  <img width="1600" height="900" alt="Screenshot (1292)" src="https://github.com/user-attachments/assets/aafe013c-5816-45d1-af45-6270afcd694a" />

      
   
# TASK 4 :
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



# TASK 5:
TEST TERMINATION PROCESS

Under task five i had to do the following
- Navigate to instance, and then select the web server you just created
- Under instance menu select the termination delete tab
- Bescause he it did not work, go to actions > select instance setting > change protection then uncheck ENABLE
- Go to actions again instance state > terminate instance
  THIS IS THE OUTCOME
  <img width="1600" height="900" alt="Screenshot (1294)" src="https://github.com/user-attachments/assets/429b93a7-4133-45b8-b5ec-a05ce8ecb84d" />


  <img width="1600" height="900" alt="Screenshot (1295)" src="https://github.com/user-attachments/assets/7c524d9c-3e11-4367-b1a0-5da26498799b" />

  ## WHAT I LEARNED
  Here's what I learned from this lab:
  - I set up a web server using AWS by launching an EC2 instance and enabling termination protection to prevent accidental deletion
  -  I monitored the performance of my server to ensure everything was functioning properly
  - I adjusted the security settings to allow web access so visitors could access my website via HTTP.
  - I learned how to scale my server, adjusting its power as needed based on my requirements.
  -  I tested the termination protection by attempting to delete the server to confirm the safety feature worked as intended
  -   Finally, I correctly shut down and removed the instance once I was done.
    # Overall :

  I gained practical experience with the key aspects of managing and operating a cloud server.


##  Lab Complete 🎓

