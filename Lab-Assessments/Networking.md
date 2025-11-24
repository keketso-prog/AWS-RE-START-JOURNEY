# NETWORKING 263
Under networking we had a few labs, i will show 2 labs i found challenging

# FIRST LAB: Create Subnets and Allocate IP addresses in an Amazon Virtual Private Cloud (Amazon VPC)
- Summarize the customer scenario
- Create a Amazon Virtual Private Cloud (Amazon VPC) and understand how to create subnets and allocate IP addresses
- Familiarize yourself with the Amazon Web Services (AWS) Management Console
- Develop a solution to the customer's issue in this lab
- Summarize and describe your findings (group activity)
# Task 1: Investigate the customer's needs
- Type and search for VPC
- Launch VPC Wizard
- Configure the following options:

- For IPv6 CIDR block, leave No IPv6 CIDR Block selected. You will not be using IPv6 in this lab.
- For the VPC name, enter First VPC
- For Public subnet's IPv4 CIDR, this option prefills. Input the correct VPC CIDR that you are using; however, keep in mind that the public subnet's CIDR must be smaller then - the VPC CIDR block, and it must be able to include at least 50 IP addresses.
- For Availability Zone, choose No Preference.
- For Subnet name, leave this option set to Public subnet.
- Leave the remaining options set to their default settings.
-  Create VPC.
# Now configure the following options:

- Choose VPC with a Single Public Subnet.
- Choose Select to move to the next step

# Task 2: Send the response to the customer
- walk through how i would build the VPC in email format

# WHAT I LEARNED
Here’s what I learned from this lab:
- I reviewed the customer’s problem to understand their networking needs and what kind of cloud environment they required
- I built an Amazon VPC and learned how to set up subnets and assign IP addresses, which is like designing separate network sections for different resources.
- I became familiar with navigating the AWS Console to manage networking, resources, and configurations more efficiently
- Using what I learned, I created a practical solution that addressed the customer’s requirements within the VPC
# OVERALL
I learned how to analyze a customer scenario, design a VPC, configure its network components, and present a clear solution — core skills for cloud architecture and troubleshooting in AWS.
 # Lab complete 🎓

# SECOND LAB: Build Your VPC and Launch a Web Server 267

Objectives
After completing this lab, you should be able to:

- Create a virtual private cloud (VPC)
- Create subnets
- Configure a security group
- Launch an Amazon Elastic Compute Cloud (Amazon EC2) instance into a VPC
  # Task 1: Create your VPC
  - search for VPC
  - Create VPC
  - View VPC

 # Task 2: Create additional subnets
 - choose Subnets
 - choose Create subnet
 - choose Create subnet
# Task 3: Associate the subnets and add routes
- choose Route Tables
- Choose Public Route Table
- Private Route Table
- Save associations
# Task 4: Create a VPC security group
- choose Security Groups
- Add rule
- Create security group.

# Task 5: Launch a web server instance
- choose EC2
- choose Instances
- Launch instances
- Choose Launch instance.

# WHAT I LEARNED
 Here’s what I learned from this lab:
- I set up a VPC, which acts like a private network in the cloud where I can place and control my resources.
- I created subnets to organize the network, allowing me to separate resources into different sections for better management and security.
- I set up a security group to control which types of traffic are allowed in and out of my instance, similar to creating a firewall for my cloud resources
- I deployed an EC2 virtual server inside the VPC, connecting it to the subnets and securing it with the configured security group

  # OVEALL
I learned how to build a complete cloud network environment by creating a VPC, structuring it with subnets, securing it with a security group, and launching an EC2 instance within it — essential steps for designing and deploying applications in AWS.

 # Lab complete 🎓
