# NETWORKING 
Under networking we had a few labs, i will show 2 labs i found challenging

# FIRST LAB: Create Subnets and Allocate IP addresses in an Amazon Virtual Private Cloud (Amazon VPC)
- Summarize the customer scenario
- Create a Amazon Virtual Private Cloud (Amazon VPC) and understand how to create subnets and allocate IP addresses
- Familiarize yourself with the Amazon Web Services (AWS) Management Console
- Develop a solution to the customer's issue in this lab
- Summarize and describe your findings (group activity)

  <img width="951" height="621" alt="Screenshot (1535)" src="https://github.com/user-attachments/assets/48d29e21-7ff9-4b83-b6b0-42c48703af10" />

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

<img width="1600" height="763" alt="Screenshot (1532)" src="https://github.com/user-attachments/assets/fa5f5d6d-eecb-47fe-aa7e-e2e13993b764" />

 <img width="1587" height="752" alt="Screenshot (1533)" src="https://github.com/user-attachments/assets/21e5b2b0-f0d7-402a-843b-26fc646c893a" />

<img width="1550" height="751" alt="Screenshot (1534)" src="https://github.com/user-attachments/assets/02e8e725-ee79-4da1-beb9-aa2bb20fed6c" />

# Task 2: Send the response to the customer
- walk through how i would build the VPC in email format:

  In this task, I independently finished the VPC configuration, functioning as both the client and the cloud support technician. I began by designing the VPC layout, selecting the CIDR block to guarantee sufficient IP addresses for every subnet. I subsequently established both public and private subnets to distinguish resources according to access needs. Subsequently, I configured the routing tables, connecting public subnets to an internet gateway for internet communication, while ensuring private subnets remained isolated. I additionally set up security groups and network ACLs to manage traffic flow securely. During the process, I assessed connectivity between subnets and confirmed that resources within the VPC were able to communicate as anticipated. By managing the setup on my own, I gained a comprehensive insight into how every element of a VPC—subnets, routing tables, gateways, and security rules—interconnects to establish an effective and safe cloud network. This task not only strengthened my technical abilities but also enabled me to consider both the customer's and engineer's viewpoints, which is essential for creating effective cloud architectures

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

<img width="1097" height="488" alt="Screenshot (1536)" src="https://github.com/user-attachments/assets/e4d7a129-66ec-4ff0-89d7-9defe10b2660" />


  # Task 1: Create your VPC
  - search for VPC
  - Create VPC
  - View VPC

  <img width="1581" height="748" alt="Screenshot (1537)" src="https://github.com/user-attachments/assets/997b15d2-3e2d-4795-a4ad-07ed25d5136b" />
 
 <img width="1552" height="754" alt="Screenshot (1538)" src="https://github.com/user-attachments/assets/020f46f3-df4e-476e-97b9-43bef8c4ea25" />

  <img width="1556" height="754" alt="Screenshot (1539)" src="https://github.com/user-attachments/assets/d587a0d5-e2ea-427e-9a23-667723035a5b" />

<img width="1524" height="754" alt="Screenshot (1540)" src="https://github.com/user-attachments/assets/fcf1b5fa-c4fd-484e-923a-18b32eb754f3" />

<img width="1568" height="752" alt="Screenshot (1541)" src="https://github.com/user-attachments/assets/58674793-fde1-45dc-bece-5a51016e3365" />

<img width="1576" height="752" alt="Screenshot (1542)" src="https://github.com/user-attachments/assets/8f815cd7-eef8-4ef7-a3ef-9b8ea944b972" />

<img width="1578" height="755" alt="Screenshot (1543)" src="https://github.com/user-attachments/assets/57177b40-fc00-4c27-b423-f97ce85aa652" />

<img width="1587" height="752" alt="Screenshot (1544)" src="https://github.com/user-attachments/assets/c3627ee5-a6a4-400c-a64b-174a5ed55f17" />

 # Task 2: Create additional subnets
 - choose Subnets
 - choose Create subnet
 - choose Create subnet

<img width="1568" height="749" alt="Screenshot (1546)" src="https://github.com/user-attachments/assets/2bc92402-feb4-40fa-8c41-29558277220b" />

<img width="1579" height="746" alt="Screenshot (1547)" src="https://github.com/user-attachments/assets/fea4fc92-50c0-487d-864c-279ed159f6d8" />

<img width="1568" height="740" alt="Screenshot (1548)" src="https://github.com/user-attachments/assets/b117dc4a-7048-4961-a947-a95b5eaf2078" />

<img width="1574" height="751" alt="Screenshot (1549)" src="https://github.com/user-attachments/assets/b826cee8-74d8-4c25-ad12-75361e771f8d" />

<img width="1572" height="746" alt="Screenshot (1550)" src="https://github.com/user-attachments/assets/eac60dfa-5aed-4a66-a536-ae2c8505cc80" />

<img width="1582" height="757" alt="Screenshot (1551)" src="https://github.com/user-attachments/assets/7c2fa29d-2918-4122-985c-cb39a42bd3c4" />

<img width="1594" height="754" alt="Screenshot (1552)" src="https://github.com/user-attachments/assets/345d40cd-0dec-4582-98cc-c1953c2fab89" />

<img width="1584" height="745" alt="Screenshot (1553)" src="https://github.com/user-attachments/assets/cc0b10ce-28b1-4415-88c1-6bce42eaebd9" />

   
# Task 3: Associate the subnets and add routes
- choose Route Tables
- Choose Public Route Table
- Private Route Table
- Save associations

<img width="1590" height="754" alt="Screenshot (1554)" src="https://github.com/user-attachments/assets/b203cef7-cc05-4d29-aab8-bc3b955cf3c7" />

<img width="1591" height="757" alt="Screenshot (1555)" src="https://github.com/user-attachments/assets/abce8ee0-45eb-4ef2-9364-fc8204c54f27" />

<img width="1581" height="749" alt="Screenshot (1556)" src="https://github.com/user-attachments/assets/2b2e2dcd-ce3e-4fb4-ac03-3bb58c9a713f" />

<img width="1581" height="749" alt="Screenshot (1557)" src="https://github.com/user-attachments/assets/0a8ff058-d22e-43c8-b794-d90c6a70c453" />

<img width="1568" height="740" alt="Screenshot (1548)" src="https://github.com/user-attachments/assets/b7065bf4-fd10-44ca-8b58-7a8e9bd31487" />

  
# Task 4: Create a VPC security group
- choose Security Groups
- Add rule
- Create security group.

<img width="1585" height="754" alt="Screenshot (1559)" src="https://github.com/user-attachments/assets/5597a47a-0c82-480c-b02a-c3a193db0956" />

<img width="1600" height="900" alt="Screenshot (1560)" src="https://github.com/user-attachments/assets/459f2713-451b-410e-a15b-22b67780c6bc" />

<img width="1587" height="746" alt="Screenshot (1561)" src="https://github.com/user-attachments/assets/8d838a76-6da5-4e85-9b46-fcb40fd7c0ae" />


# Task 5: Launch a web server instance
- choose EC2
- choose Instances
- Launch instances
- Choose Launch instance.

<img width="1581" height="751" alt="Screenshot (1562)" src="https://github.com/user-attachments/assets/2bba5178-c7a4-4b7b-ac67-1f52104f035c" />

<img width="1590" height="749" alt="Screenshot (1563)" src="https://github.com/user-attachments/assets/3cffa419-c9cc-44b0-9527-e6b406ea2def" />

<img width="1578" height="763" alt="Screenshot (1564)" src="https://github.com/user-attachments/assets/dd1772ab-8868-40b5-a9b5-de0a604384f2" />

<img width="1590" height="749" alt="Screenshot (1565)" src="https://github.com/user-attachments/assets/ab687c41-4e10-464c-b0be-fed594118fba" />

<img width="1587" height="746" alt="Screenshot (1566)" src="https://github.com/user-attachments/assets/dbfec012-b691-4033-9bda-b01db61c0f69" />

<img width="1585" height="746" alt="Screenshot (1567)" src="https://github.com/user-attachments/assets/17002d09-6fd2-48f9-974a-6e3fb1de8c8b" />

<img width="1600" height="900" alt="Screenshot (1568)" src="https://github.com/user-attachments/assets/1a04ee8e-efbe-4c60-9332-9eca9e1fe0ba" />
  
<img width="1600" height="900" alt="Screenshot (1570)" src="https://github.com/user-attachments/assets/160a1e65-374f-4203-9f4c-ebdaa73e81f2" />

<img width="927" height="329" alt="Screenshot (1572)" src="https://github.com/user-attachments/assets/0cbad045-4f62-4b9b-8a67-6fd76f277e88" />

<img width="920" height="408" alt="Screenshot (1573)" src="https://github.com/user-attachments/assets/5ddf0639-bf86-40db-8e30-646112db0ec8" />

# WHAT I LEARNED
 Here’s what I learned from this lab:
- I set up a VPC, which acts like a private network in the cloud where I can place and control my resources.
- I created subnets to organize the network, allowing me to separate resources into different sections for better management and security.
- I set up a security group to control which types of traffic are allowed in and out of my instance, similar to creating a firewall for my cloud resources
- I deployed an EC2 virtual server inside the VPC, connecting it to the subnets and securing it with the configured security group

  # OVEALL
I learned how to build a complete cloud network environment by creating a VPC, structuring it with subnets, securing it with a security group, and launching an EC2 instance within it — essential steps for designing and deploying applications in AWS.

 # Lab complete 🎓
