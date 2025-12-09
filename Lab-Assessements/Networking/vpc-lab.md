# Create Subnets and Allocate IP addresses in an Amazon Virtual Private Cloud (Amazon VPC)

<img width="951" height="621" alt="Screenshot (1535)" src="https://github.com/user-attachments/assets/48d29e21-7ff9-4b83-b6b0-42c48703af10" />

I worked through a hands-on lab with Amazon VPC, learning how to design and create a virtual private cloud to meet a customer's networking requirements. 

- Here's what I did.

# Task 1: Investigating the Customer's Needs
I started by understanding the customer scenario and their specific networking requirements. Then I navigated to the AWS Management Console, searched for "VPC," and launched the VPC Wizard to begin creating the network infrastructure.
# Configuring the VPC
I configured the VPC with the following settings:

- IPv6 CIDR block: Left as "No IPv6 CIDR Block" since IPv6 wasn't required for this lab
- VPC name: Entered "First VPC"
- Public subnet's IPv4 CIDR: Configured the CIDR block to be smaller than the VPC CIDR while ensuring it could accommodate at least 50 IP addresses
- Availability Zone: Selected "No Preference"
- Subnet name: Left as "Public subnet"
- Left all remaining options at their default settings

I then clicked "Create VPC" to build the network infrastructure.

<img width="1581" height="748" alt="Screenshot (1537)" src="https://github.com/user-attachments/assets/997b15d2-3e2d-4795-a4ad-07ed25d5136b" />
<img width="1552" height="754" alt="Screenshot (1538)" src="https://github.com/user-attachments/assets/020f46f3-df4e-476e-97b9-43bef8c4ea25" />
<img width="1556" height="754" alt="Screenshot (1539)" src="https://github.com/user-attachments/assets/d587a0d5-e2ea-427e-9a23-667723035a5b" />
<img width="1524" height="754" alt="Screenshot (1540)" src="https://github.com/user-attachments/assets/fcf1b5fa-c4fd-484e-923a-18b32eb754f3" />
<img width="1568" height="752" alt="Screenshot (1541)" src="https://github.com/user-attachments/assets/58674793-fde1-45dc-bece-5a51016e3365" />
<img width="1576" height="752" alt="Screenshot (1542)" src="https://github.com/user-attachments/assets/8f815cd7-eef8-4ef7-a3ef-9b8ea944b972" />
<img width="1578" height="755" alt="Screenshot (1543)" src="https://github.com/user-attachments/assets/57177b40-fc00-4c27-b423-f97ce85aa652" />


# Task 2: Send the response to the customer
- walk through how i would build the VPC in email format:

  In this task, I independently finished the VPC configuration, functioning as both the client and the cloud support technician. I began by designing the VPC layout, selecting the CIDR block to guarantee sufficient IP addresses for every subnet. I subsequently established both public and private subnets to distinguish resources according to access needs. Subsequently, I configured the routing tables, connecting public subnets to an internet gateway for internet communication, while ensuring private subnets remained isolated. I additionally set up security groups and network ACLs to manage traffic flow securely. During the process, I assessed connectivity between subnets and confirmed that resources within the VPC were able to communicate as anticipated. By managing the setup on my own, I gained a comprehensive insight into how every element of a VPC—subnets, routing tables, gateways, and security rules—interconnects to establish an effective and safe cloud network. This task not only strengthened my technical abilities but also enabled me to consider both the customer's and engineer's viewpoints, which is essential for creating effective cloud architectures
# CHALLENGES
I initially struggled with understanding CIDR block notation and calculating the correct subnet size. I had to figure out how to ensure my public subnet CIDR was smaller than the VPC CIDR while still providing enough IP addresses (at least 50
# WHAT I LEARNED
Here’s what I learned from this lab:
- I reviewed the customer’s problem to understand their networking needs and what kind of cloud environment they required
- I built an Amazon VPC and learned how to set up subnets and assign IP addresses, which is like designing separate network sections for different resources.
- I became familiar with navigating the AWS Console to manage networking, resources, and configurations more efficiently
- Using what I learned, I created a practical solution that addressed the customer’s requirements within the VPC
# OVERALL
I learned how to analyze a customer scenario, design a VPC, configure its network components, and present a clear solution — core skills for cloud architecture and troubleshooting in AWS.
 # Lab complete 🎓


