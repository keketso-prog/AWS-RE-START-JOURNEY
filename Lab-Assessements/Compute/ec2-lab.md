# EC2

<img width="549" height="383" alt="Screenshot (1296)" src="https://github.com/user-attachments/assets/e997b55c-8e84-42bc-be40-93d47953422e" />

I worked through a hands-on lab with Amazon EC2, learning how to launch, configure, monitor, modify, and manage EC2 instances. Here's what I did.
Starting the Lab
I started the lab environment and navigated to the EC2 service in the AWS Management Console to begin launching my instance.
# Task 1: Launching an EC2 Instance
I clicked "Launch instance" and configured the following settings:

- Instance name: Gave my instance a descriptive name (Web Server)
- Amazon Machine Image (AMI): Selected an appropriate AMI (such as Amazon Linux 2)
- Instance type: Chose an instance type (initially t3.micro)
- Key pair: Configured or selected an existing key pair for SSH access
- Network settings: Selected the appropriate VPC and subnet, and configured the security group
- Storage: Added and configured the storage volume (8GB by default)
- Advanced settings: Enabled termination protection to prevent accidental deletion

I then launched the instance and waited for it to enter the "running" state.

<img width="1600" height="900" alt="Screenshot (1289)" src="https://github.com/user-attachments/assets/ee7a4d40-d86f-4b4f-b547-aec3bead5cda" />

# Task 2: Monitoring the Instance
I selected my running instance and explored the monitoring features:

- Reviewed the Status Checks tab to verify system and instance reachability
- Examined the Monitoring tab to view CloudWatch metrics like CPU utilization, network traffic, and disk I/O
- Used these metrics to understand instance performance and troubleshoot any potential issues

<img width="1600" height="900" alt="Screenshot (1290)" src="https://github.com/user-attachments/assets/869d8dd6-32c1-4142-91b3-e084294f481a" /> 

# Task 3: Updating Security Rules and Accessing the Web Server
I needed to allow HTTP access to my web server:

- Navigated to Network & Security and selected Security Groups
- Selected the security group associated with my instance
- Clicked on the Inbound rules tab and selected "Edit inbound rules"
- Added a new rule with:

Type: HTTP
Source: Anywhere-IPv4 (0.0.0.0/0)


- Saved the rules

I then copied the instance's public IP address and pasted it into a browser to access the web server. The webpage loaded successfully, confirming that HTTP traffic was now allowed.

<img width="1600" height="900" alt="Screenshot (1291)" src="https://github.com/user-attachments/assets/64b7336e-63ba-46eb-82ab-e92095e1cf8a" />
<img width="1600" height="900" alt="Screenshot (1292)" src="https://github.com/user-attachments/assets/aafe013c-5816-45d1-af45-6270afcd694a" />

# Task 4: Resizing the Instance
To scale my instance, I performed the following steps:

- Selected my web server instance
- Chose Instance state > Stop instance and waited until the status showed "Stopped"
- Selected Actions > Instance settings > Change instance type
- Changed the instance type from t3.micro to t3.small
- Selected Actions > Storage and modified the volume size from 8GB to 10GB
Started the instance again

The instance successfully restarted with the new configuration, displaying the updated instance type and storage capacity.

<img width="1600" height="900" alt="Screenshot (1293)" src="https://github.com/user-attachments/assets/03ce1736-f693-44da-91b6-9242d756dfd4" />

# Task 5: Testing Termination Protection
I tested the termination protection feature:

- Selected my web server instance
Attempted to terminate it by selecting Instance state > Terminate instance
The termination failed because termination protection was enabled

<img width="1600" height="900" alt="Screenshot (1294)" src="https://github.com/user-attachments/assets/429b93a7-4133-45b8-b5ec-a05ce8ecb84d" />

# To successfully terminate the instance:

- Went to Actions > Instance settings > Change termination protection
- Unchecked the "Enable" box to disable termination protection
- Returned to Actions > Instance state > Terminate instance
- Confirmed the termination, and the instance was successfully terminated

<img width="1600" height="900" alt="Screenshot (1295)" src="https://github.com/user-attachments/assets/7c524d9c-3e11-4367-b1a0-5da26498799b" />


# CHALLENGES
I initially struggled with understanding why my web server wasn't accessible in the browser even though the instance was running. After troubleshooting, I realized the security group didn't have an inbound rule allowing HTTP traffic on port 80. Once I added the HTTP rule with source set to Anywhere-IPv4, the web server became accessible immediately. This taught me the importance of properly configuring security groups for different types of applications.

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
  

  




