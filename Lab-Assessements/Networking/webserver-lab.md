# Build Your VPC and Launch a Web Server

<img width="1097" height="488" alt="Screenshot (1536)" src="https://github.com/user-attachments/assets/e4d7a129-66ec-4ff0-89d7-9defe10b2660" />

I worked through a hands-on lab with Amazon VPC, learning how to create a complete virtual network infrastructure and launch an EC2 instance within it. 

Here's what I did.
# Task 1: Creating the VPC
I searched for "VPC" in the AWS Management Console and clicked "Create VPC." I configured the VPC settings and created it, then viewed the VPC details to confirm it was successfully created.

<img width="1552" height="754" alt="Screenshot (1538)" src="https://github.com/user-attachments/assets/020f46f3-df4e-476e-97b9-43bef8c4ea25" />
<img width="1578" height="755" alt="Screenshot (1543)" src="https://github.com/user-attachments/assets/57177b40-fc00-4c27-b423-f97ce85aa652" />
<img width="1587" height="752" alt="Screenshot (1544)" src="https://github.com/user-attachments/assets/c3627ee5-a6a4-400c-a64b-174a5ed55f17" />

# Task 2: Creating Additional Subnets
I navigated to the Subnets section and clicked "Create subnet." I created multiple subnets within my VPC to organize my network resources, repeating the process as needed.

<img width="1568" height="749" alt="Screenshot (1546)" src="https://github.com/user-attachments/assets/2bc92402-feb4-40fa-8c41-29558277220b" />
<img width="1579" height="746" alt="Screenshot (1547)" src="https://github.com/user-attachments/assets/fea4fc92-50c0-487d-864c-279ed159f6d8" />

# Task 3: Associating Subnets and Adding Routes

I went to Route Tables and configured both public and private route tables. I associated the appropriate subnets with each route table and saved the associations to establish proper network routing.

<img width="1584" height="745" alt="Screenshot (1553)" src="https://github.com/user-attachments/assets/cc0b10ce-28b1-4415-88c1-6bce42eaebd9" />
<img width="1590" height="754" alt="Screenshot (1554)" src="https://github.com/user-attachments/assets/b203cef7-cc05-4d29-aab8-bc3b955cf3c7" />
<img width="1591" height="757" alt="Screenshot (1555)" src="https://github.com/user-attachments/assets/abce8ee0-45eb-4ef2-9364-fc8204c54f27" />

# Task 4: Creating a VPC Security Group
I selected Security Groups and created a new security group. I added inbound and outbound rules to control traffic, then saved the security group configuration.

<img width="1600" height="900" alt="Screenshot (1560)" src="https://github.com/user-attachments/assets/459f2713-451b-410e-a15b-22b67780c6bc" />
<img width="1587" height="746" alt="Screenshot (1561)" src="https://github.com/user-attachments/assets/8d838a76-6da5-4e85-9b46-fcb40fd7c0ae" />

# Task 5: Launching a Web Server Instance
I navigated to EC2, selected Instances, and clicked "Launch instances." I configured the instance to run within my VPC, selected the appropriate subnet and security group, and launched the web server instance.

<img width="1590" height="749" alt="Screenshot (1563)" src="https://github.com/user-attachments/assets/3cffa419-c9cc-44b0-9527-e6b406ea2def" />
<img width="1600" height="900" alt="Screenshot (1568)" src="https://github.com/user-attachments/assets/1a04ee8e-efbe-4c60-9332-9eca9e1fe0ba" />
<img width="1600" height="900" alt="Screenshot (1570)" src="https://github.com/user-attachments/assets/160a1e65-374f-4203-9f4c-ebdaa73e81f2" />
<img width="927" height="329" alt="Screenshot (1572)" src="https://github.com/user-attachments/assets/0cbad045-4f62-4b9b-8a67-6fd76f277e88" />
<img width="920" height="408" alt="Screenshot (1573)" src="https://github.com/user-attachments/assets/5ddf0639-bf86-40db-8e30-646112db0ec8" />

# CHALLENGES
I got confused when associating subnets with route tables—specifically understanding which subnets should be associated with the public route table versus the private route table. I had to carefully think through which subnets needed internet access through an internet gateway and which ones should remain private.

# WHAT I LEARNED
 Here’s what I learned from this lab:
- I set up a VPC, which acts like a private network in the cloud where I can place and control my resources.
- I created subnets to organize the network, allowing me to separate resources into different sections for better management and security.
- I set up a security group to control which types of traffic are allowed in and out of my instance, similar to creating a firewall for my cloud resources
- I deployed an EC2 virtual server inside the VPC, connecting it to the subnets and securing it with the configured security group

  # OVEALL
I learned how to build a complete cloud network environment by creating a VPC, structuring it with subnets, securing it with a security group, and launching an EC2 instance within it — essential steps for designing and deploying applications in AWS.

 # Lab complete 🎓


