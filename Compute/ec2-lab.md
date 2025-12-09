EC2

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
# Task 2: Monitoring the Instance
I selected my running instance and explored the monitoring features:

- Reviewed the Status Checks tab to verify system and instance reachability
- Examined the Monitoring tab to view CloudWatch metrics like CPU utilization, network traffic, and disk I/O
- Used these metrics to understand instance performance and troubleshoot any potential issues

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
# Task 4: Resizing the Instance
To scale my instance, I performed the following steps:

- Selected my web server instance
- Chose Instance state > Stop instance and waited until the status showed "Stopped"
- Selected Actions > Instance settings > Change instance type
- Changed the instance type from t3.micro to t3.small
- Selected Actions > Storage and modified the volume size from 8GB to 10GB
Started the instance again

The instance successfully restarted with the new configuration, displaying the updated instance type and storage capacity.
# Task 5: Testing Termination Protection
I tested the termination protection feature:

- Selected my web server instance
Attempted to terminate it by selecting Instance state > Terminate instance
The termination failed because termination protection was enabled

# To successfully terminate the instance:

- Went to Actions > Instance settings > Change termination protection
- Unchecked the "Enable" box to disable termination protection
- Returned to Actions > Instance state > Terminate instance
- Confirmed the termination, and the instance was successfully terminated

