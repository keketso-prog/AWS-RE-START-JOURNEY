
WEEK 1

🌩️ What is AWS?

AWS stands for Amazon Web Services.
It is a cloud computing platform made by Amazon.

That means instead of buying and managing your own computers (servers),
you can rent computing power, storage, and tools from Amazon over the internet.

🕰️ Here is a Short History of AWS:

2002: Amazon started experimenting with web services.

2006: AWS officially launched with a few basic services:

S3 (for file storage)

EC2 (for virtual computers/servers)

SQS (for message queuing)

2010s: AWS grew fast — many startups and big companies started using it.

Today: AWS is one of the largest cloud providers in the world, along with Google Cloud and Microsoft Azure.

BELOW IS A TABLE AND EXPLANATION OF SOME OF THE SERVICES THEY OFFER:
| **Type of Service**          | **Examples**              | **Simple Meaning**                                                          |
| ---------------------------- | ------------------------- | --------------------------------------------------------------------------- |
| 💻 **Compute**               | EC2, Lambda               | Lets you run apps or websites on Amazon’s computers.                        |
| 📦 **Storage**               | S3, EBS                   | Keeps your files, photos, and backups safe online.                          |
| 🗂️ **Databases**            | RDS, DynamoDB             | Stores your data so you can find and use it easily.                         |
| 🌍 **Networking**            | VPC, CloudFront, Route 53 | Connects your apps to the internet safely and fast.                         |
| 🧠 **AI & Machine Learning** | SageMaker, Rekognition    | Helps make smart apps that can learn or see things (like face recognition). |
| 🧰 **Developer Tools**       | CodeBuild, CodeDeploy     | Helps programmers build and update apps quickly.                            |
| 🔐 **Security & Identity**   | IAM, KMS                  | Keeps your information safe and controls who can access it.                 |
| 📊 **Analytics**             | Athena, Redshift          | Helps you understand and study your data.                                   |

WHAT IS CLOUD COMPUTING?

Cloud computing is the delivery of computing services over the internet rather than using local servers or personal devices. Instead of owning and maintaining physical hardware, you rent computing resources from a provider on an as-needed basis.

THIS ARE THE CHARACTERISTICS OF CLOUD COMPUTING:
- Resources accessed via the internet
- Pay-as-you-go pricing model
- Scalable (increase or decrease resources as needed)
- No physical hardware maintenance required

    THIS ARE SOME EXAMPLES OF AWS CLOUD COMPUTING SERVICES THEY OFFER:
  
- EC2 (Elastic Compute Cloud) - Virtual servers in the cloud. You can launch different sized virtual machines with various operating systems to run your applications. 
- S3 (Simple Storage Service) - Object storage for files and data. You can store and retrieve any amount of data at any time.
- RDS (Relational Database Service) - Managed database service that handles setup, patching, and backups automatically.
- Lambda - Serverless computing where you run code without provisioning servers. 
- CloudFront - Content delivery network (CDN) that distributes your content globally. 
- VPC (Virtual Private Cloud) - Lets you create isolated virtual networks within AWS where you control IP addresses, subnets, and security settings.

  AWS SHARED RESPONSIBILITY MODEL:
  
This defines who's responsible for what between AWS and you (the customer). A simple day-to-day example is like renting an apartment:

AWS is responsible for "Security OF the Cloud":

Physical security of data centers (guards, cameras, locks)
Hardware and infrastructure (servers, storage, networking equipment)
Virtualization layer that separates customers
Maintaining the underlying services

You are responsible for "Security IN the Cloud":

Your data and content
User access management (who can access what)
Operating system patches and updates (for EC2 instances)
Application security
Firewall configurations
Encryption settings

Simple analogy: AWS builds and maintains the building, elevators, and utilities. You're responsible for locking your apartment door, managing who has keys, and securing your belongings inside.

AWS PRICING MODEL IS AS FOLLOWS:

AWS uses a pay-as-you-go model. You only pay for what you use, with no upfront costs or long-term contracts (though you can get discounts with commitments).

- Compute (EC2): Charged per second/hour the instance runs. Larger, more powerful instances cost more.
- Storage (S3): Pay per GB stored per month, plus charges for data retrieval and transfers.
- Data Transfer: Moving data OUT of AWS to the internet costs money. Data transferred IN is usually free. Data between AWS services in the same region is often free or cheap

  📝 AWS Notes - Cloud Fundamentals
💰 Fundamentals of AWS Pricing Model
What is AWS Pricing?

AWS = Amazon Web Services (cloud computing platform)
Pay-as-you-go → Only pay for what you use (like electricity bill)
No upfront costs or long-term contracts required

💵 3 Main Pricing Models:

Pay-as-you-go 💳

Pay only when you use services
No minimum fees
Stop paying when you stop using


Save when you reserve 🎟️

Commit to 1 or 3 years
Get big discounts (up to 75%)
Good for steady, predictable usage


Pay less by using more 📊

Volume discounts
Use more = cheaper per unit
Like buying in bulk at a store



🆓 Free Tier:

AWS gives free usage limits for 12 months
Great for learning and testing
Examples: 750 hours of EC2, 5GB storage

💡 What You Pay For:

Compute → Processing power (running programs)
Storage → Saving data (like hard drive)
Data Transfer → Moving data in/out of AWS
Network → Internet bandwidth used

🎯 Cost Optimization Tips:

Turn off resources when not using
Use right-sized instances (don't pay for more than you need)
Monitor usage with AWS Cost Explorer
Set billing alerts to avoid surprises


🖥️ Amazon EC2 (Elastic Compute Cloud)
What is EC2?

Virtual computers in the cloud ☁️
Like renting a computer you can access from anywhere
Can start/stop anytime
Elastic = Can grow or shrink based on needs

🔑 Key Concepts:
Instance → Your virtual server (like a computer)

Choose size (CPU, RAM, storage)
Choose operating system (Linux, Windows, etc.)

Instance Types:

t2.micro → Small (free tier eligible)
t2.medium → Medium power
c5.large → High CPU for calculations
r5.large → High RAM for memory-heavy tasks

📦 Components:

AMI (Amazon Machine Image) 📸

Template for your instance
Pre-configured OS and software
Like a blueprint for building a house


Instance Types 🎛️

Different sizes and capabilities
General Purpose: Balanced (t2, t3)
Compute Optimized: Fast processing (c5, c6)
Memory Optimized: Lots of RAM (r5, r6)
Storage Optimized: Fast disk access (i3, d2)


Security Groups 🔒

Virtual firewall
Controls who can access your instance
Set rules for incoming/outgoing traffic


Key Pairs 🔑

Used to login securely (SSH)
Public key (AWS keeps) + Private key (you keep)



🚀 Launching an EC2 Instance:

Choose AMI (operating system)
Choose instance type (size)
Configure network settings
Add storage
Configure security group
Create/select key pair
Launch! 🎉

💰 EC2 Pricing Options:

On-Demand 💳

Pay by the hour/second
No commitment
Most flexible but most expensive


Reserved Instances 🎟️

1 or 3 year commitment
Save up to 75%
Good for steady workloads


Spot Instances 🎰

Bid on unused capacity
Save up to 90%
Can be interrupted (AWS takes it back)
Good for flexible jobs


Savings Plans 💼

Commit to spending amount per hour
Flexible on instance types
Save up to 72%



⚙️ Important Features:

Elastic IP → Fixed IP address (doesn't change)
Auto Scaling → Automatically add/remove instances based on demand
Load Balancer → Distribute traffic across multiple instances
EBS (Elastic Block Store) → Hard drive for your instance

📊 EC2 States:

Running 🟢 → Active (you pay)
Stopped 🟡 → Turned off (only pay for storage)
Terminated 🔴 → Deleted forever


☁️ Cloud Foundations
What is Cloud Computing?

Using someone else's computers over the internet
No need to buy physical servers
Access from anywhere with internet

🌟 Benefits of Cloud:

No upfront costs 💰

Don't buy expensive hardware
Pay only for what you use


Stop guessing capacity 🎯

Scale up when busy
Scale down when quiet
No wasted resources


Massive economies of scale 📈

AWS buys in bulk → passes savings to you
Cheaper than doing it yourself


Speed and agility ⚡

Deploy in minutes, not months
Experiment quickly
Fail fast, learn fast


Global in minutes 🌍

Deploy apps worldwide
Multiple regions (US, Europe, Asia, etc.)
Low latency for users everywhere


Focus on business 🎯

AWS handles hardware/infrastructure
You focus on building your app



☁️ Types of Cloud Services:

IaaS (Infrastructure as a Service) 🏗️

Basic building blocks
You control OS, network, storage
Example: EC2
Like renting land to build your house


PaaS (Platform as a Service) 🛠️

AWS manages OS, runtime
You just deploy your code
Example: Elastic Beanstalk
Like renting a house, you just add furniture


SaaS (Software as a Service) 📱

Fully managed application
You just use it
Example: Gmail, Dropbox
Like staying at a hotel with everything included



🌍 AWS Global Infrastructure:
Regions 🗺️

Physical locations around the world
Examples: us-east-1 (Virginia), eu-west-1 (Ireland)
Choose region closest to your users

Availability Zones (AZ) 🏢

Data centers within a region
Each region has multiple AZs (usually 3-6)
Isolated from each other (for backup)
Connected with high-speed networks

Edge Locations 📡

Cache content closer to users
Faster delivery (CDN)
Used by CloudFront

🔐 AWS Shared Responsibility Model:
AWS Responsibility → Security OF the cloud

Physical security
Hardware maintenance
Network infrastructure
Virtualization layer

Your Responsibility → Security IN the cloud

Data encryption
Firewall rules
User access
Application security
Operating system updates

Think of it like an apartment: 🏢

Landlord (AWS) secures building
You secure your apartment

💡 Core AWS Services (Quick Overview):
Compute 💻

EC2: Virtual servers
Lambda: Run code without servers

Storage 💾

S3: Object storage (files, images)
EBS: Hard drives for EC2

Database 🗄️

RDS: Managed databases (MySQL, PostgreSQL)
DynamoDB: NoSQL database

Network 🌐

VPC: Private network
Route 53: DNS service
CloudFront: Content delivery (CDN)

Security 🔒

IAM: User access management
Security Groups: Firewalls

📊 Well-Architected Framework (5 Pillars):

Operational Excellence ⚙️ → Run and monitor systems
Security 🔐 → Protect data and systems
Reliability 💪 → Recover from failures
Performance Efficiency ⚡ → Use resources efficiently
Cost Optimization 💰 → Avoid unnecessary costs


🎓 Quick Tips & Best Practices
✅ Start small → Use free tier to learn
✅ Set billing alarms → Avoid surprise costs
✅ Stop instances when not needed → Save money
✅ Use multiple AZs → High availability
✅ Tag everything → Organize and track costs
✅ Security first → Never share keys, use IAM roles
✅ Backup regularly → Use snapshots for EC2/EBS

🔥 Common Beginner Mistakes to Avoid
❌ Leaving instances running 24/7 (when you only need them 8 hours)
❌ Using wrong instance size (too big = waste money)
❌ Not setting billing alerts
❌ Storing access keys in code
❌ Not backing up data
❌ Using default security settings

🚀 Remember: Cloud is about flexibility and paying only for what you use. Start experimenting and learning! Practice makes perfect! 💪RetryClaude can make mistakes. Please double-check responses. Sonnet 4.5

WEEK 2

📝 Week 2 - Linux Notes
🐧 Introduction to Linux

What is Linux? → An operating system like Windows or Mac, but it's free and open-source
Why Linux? → Powerful, secure, and used in servers, phones (Android), and supercomputers
Distros → Different flavors like Ubuntu, Fedora, CentOS (all are Linux but look different)


💻 Linux Command Lines

Terminal/Shell → The black screen where you type commands
Basic commands:

pwd → Print Working Directory (where am I?)
ls → List files and folders
cd → Change directory (move to different folder)
clear → Clean your screen
exit → Close terminal




✏️ Editing Files

Text editors:

nano → Easy for beginners (Ctrl+X to exit)
vim → Powerful but harder (press i to insert, :wq to save & quit)
gedit → GUI editor (if you have desktop)


Example: nano myfile.txt opens the file to edit


📁 Working with Files

Create file: touch filename.txt
Copy file: cp source.txt destination.txt
Move/Rename: mv oldname.txt newname.txt
Delete file: rm filename.txt ⚠️ (careful! no undo)
View file: cat filename.txt (shows content)
Create folder: mkdir foldername
Delete folder: rmdir foldername (only empty folders) or rm -r foldername (deletes everything inside)


🔐 Managing File Permissions

Permission types:

r → Read (can view)
w → Write (can edit)
x → Execute (can run as program)


Who gets permissions:

Owner → The person who created it
Group → Team members
Others → Everyone else


View permissions: ls -l (shows like: -rwxr-xr--)
Change permissions: chmod 755 filename or chmod +x script.sh
Change owner: chown username filename


⚙️ Working with Commands

Get help: man command (manual) or command --help
Command structure: command -options arguments
Examples:

ls -la → List all files with details
rm -rf folder → Force delete folder


History: history shows all previous commands
Shortcuts:

↑ → Previous command
Tab → Auto-complete
Ctrl+C → Stop running command




🔄 Managing Processes

Process → A running program
View processes: ps or top (live view)
Kill process: kill PID (PID = process ID number)
Force kill: kill -9 PID 💀
Background jobs: Add & at end → command &
Foreground job: fg
Check running: jobs


🎯 Managing Services

Service → Programs that run in background (like web server, database)
Commands (systemd):

systemctl start servicename → Start service
systemctl stop servicename → Stop service
systemctl restart servicename → Restart service
systemctl status servicename → Check if running
systemctl enable servicename → Auto-start on boot
systemctl disable servicename → Don't auto-start




🐚 Bash Shell

Bash → The default Linux command language
Variables:

Create: NAME="John"
Use: echo $NAME


Environment variables: echo $PATH, echo $HOME
Special characters:

| → Pipe (send output to next command)
> → Redirect output to file
>> → Append to file
* → Wildcard (all files)




📜 Bash Shell Scripting

Script → A file with multiple commands
Create script:

nano script.sh
First line: #!/bin/bash
Add commands
Save and exit


Make executable: chmod +x script.sh
Run script: ./script.sh
Basic scripting:

bash  #!/bin/bash
  echo "Hello World"
  NAME="Linux"
  echo "Learning $NAME"

📦 Software Management

Package → Software you install
Package managers:

Ubuntu/Debian: apt

Install: sudo apt install package
Update: sudo apt update && sudo apt upgrade
Remove: sudo apt remove package


RedHat/CentOS: yum or dnf

Install: sudo yum install package
Update: sudo yum update






📋 Managing Log Files

Logs → Records of what happened in the system
Location: /var/log/
Important logs:

/var/log/syslog → System messages
/var/log/auth.log → Login attempts
/var/log/dmesg → Boot messages


View logs:

cat /var/log/syslog → See all
tail -f /var/log/syslog → Watch live updates
head /var/log/syslog → See first lines


journalctl → Modern log viewer (systemd)


🚀 Advanced Bash Shell Scripting

Conditionals (if statements):

bash  if [ $AGE -gt 18 ]; then
    echo "Adult"

    📝 Week 3 
    
    Networking Notes🌐 Networking ConceptsWhat is a Network?

Computers connected together to share information
Like a highway system for data 🚗
Allows devices to communicate
🔑 Key Terms:Network 🕸️

Group of connected devices
Share resources and data
Protocol 📋

Rules for communication
Like a common language computers speak
Example: HTTP, TCP/IP, FTP
Bandwidth 🚀

Speed of data transfer
Measured in Mbps or Gbps
Like width of a highway (more lanes = faster)
Latency ⏱️

Delay in communication
Measured in milliseconds (ms)
Lower is better (faster response)
Router 🔀

Directs traffic between networks
Like a traffic cop
Connects your home to the internet
Switch 🔄

Connects devices within same network
Like a distribution center
Sends data to correct device
Firewall 🔥🧱

Security barrier
Blocks unwanted traffic
Protects your network
📊 Network Types:
LAN (Local Area Network) 🏠

Small area (home, office)
Fast and secure
Example: Your home WiFi



WAN (Wide Area Network) 🌍

Large area (cities, countries)
Connects multiple LANs
Example: The Internet



VPN (Virtual Private Network) 🔐

Secure connection over internet
Encrypts your data
Like a private tunnel


🎯 OSI Model (7 Layers):
Think of it like a mail delivery system 📬
Physical 🔌 → Cables, WiFi signals (the truck)
Data Link 📡 → MAC addresses, switches (local delivery)
Network 🗺️ → IP addresses, routers (route planning)
Transport 🚚 → TCP/UDP, ports (delivery tracking)
Session 🤝 → Maintains connections (meeting appointment)
Presentation 🎨 → Encryption, formatting (wrapping the package)
Application 📱 → HTTP, FTP, email (the actual letter)
🔌 TCP vs UDP:TCP (Transmission Control Protocol) 📦✅

Reliable delivery
Checks if data arrived
Slower but accurate
Example: Web browsing, email
UDP (User Datagram Protocol) 📦⚡

Fast delivery
Doesn't check if data arrived
Faster but can lose data
Example: Video calls, gaming, streaming
🏷️ IP AddressesWhat is an IP Address?

Unique address for each device on network
Like a home address for computers 🏠
Allows devices to find each other
📍 IPv4 (Version 4):

Most common format
Looks like: 192.168.1.100
Four numbers (0-255) separated by dots
About 4.3 billion possible addresses
Running out of addresses 😰
📍 IPv6 (Version 6):

Newer format
Looks like: 2001:0db8:85a3:0000:0000:8a2e:0370:7334
Uses letters and numbers
340 undecillion addresses (almost unlimited!)
Slowly replacing IPv4
🎭 IP Address Classes (IPv4):Class A 🏢

Range: 1.0.0.0 to 126.255.255.255
For huge networks (millions of devices)
First number identifies network
Class B 🏭

Range: 128.0.0.0 to 191.255.255.255
For medium networks (thousands of devices)
First two numbers identify network
Class C 🏪

Range: 192.0.0.0 to 223.255.255.255
For small networks (254 devices)
First three numbers identify network
🔢 Special IP Addresses:
127.0.0.1 → Localhost (your own computer) 🏠
0.0.0.0 → All addresses/any address
255.255.255.255 → Broadcast (send to everyone)
🎯 Subnets & Subnet Masks:Subnet 🗂️

Divides network into smaller sections
Improves security and performance
Like dividing a building into apartments
Subnet Mask 🎭

Identifies which part is network vs device
Common: 255.255.255.0 (Class C)
Shows how many devices can fit
CIDR Notation 📝

Shorter way to write subnet mask
Example: 192.168.1.0/24
/24 means first 24 bits are network
🧮 Example:

IP: 192.168.1.10
Subnet: 255.255.255.0 or /24
Network: 192.168.1.0
Usable IPs: 192.168.1.1 to 192.168.1.254
Total devices: 254
☁️ Networking in AWS🌐 VPC (Virtual Private Cloud):

Your own private network in AWS
Like your own data center in the cloud
Isolated from other customers
Full control over network
🏗️ VPC Components:1. Subnets 🗂️

Sections of your VPC
Can be public or private
Lives in one Availability Zone
Like rooms in your house
2. Internet Gateway (IGW) 🚪🌍

Connects VPC to internet
Allows public access
Like your front door
3. NAT Gateway 🔄

Allows private subnets to access internet
But internet can't access them
One-way street for outgoing traffic
Costs money 💰
4. Route Tables 🗺️

Directions for network traffic
Tells data where to go
Each subnet has a route table
5. Network ACLs 🛡️

Firewall at subnet level
Stateless (checks both ways)
Allow/deny rules by IP
6. Security Groups 🔒

Firewall at instance level
Stateful (remembers connections)
Only allow rules (no deny)
🎯 Public vs Private Subnets:Public Subnet 🌍

Has route to Internet Gateway
Devices get public IPs
Accessible from internet
Use for: Web servers, load balancers
Private Subnet 🔐

No direct internet access
Only private IPs
More secure
Use for: Databases, application servers
📊 Common VPC Setup:
VPC (10.0.0.0/16)
├── Public Subnet (10.0.1.0/24) → IGW → Internet
│   └── Web Server (public IP)
└── Private Subnet (10.0.2.0/24) → NAT → Internet
    └── Database (private IP only)🌍 AWS Regions & AZs in Networking:

VPC spans entire region
Subnets exist in one AZ
Best practice: Use multiple AZs for redundancy
High availability setup
🌐 Public and Private IP Addresses🔓 Public IP Addresses:What are they? 🌍

Visible on the internet
Globally unique
Can be accessed from anywhere
Like your home's street address
Characteristics:

✅ Internet accessible
✅ Routable globally
✅ Must be unique worldwide
❌ Limited supply (expensive)
Use Cases:

Web servers
Email servers
Gaming servers
Anything users access directly
AWS Public IPs:

Assigned to EC2 in public subnet
Can be Elastic IP (static) or auto-assigned (dynamic)
Charged if not attached to running instance
🔒 Private IP Addresses:What are they? 🏠

Only visible within private network
Not accessible from internet
Can be reused in different networks
Like an apartment number (only meaningful inside building)
Private IP Ranges: (Reserved by IANA)

Class A: 10.0.0.0 to 10.255.255.255 (/8)
Class B: 172.16.0.0 to 172.31.255.255 (/12)
Class C: 192.168.0.0 to 192.168.255.255 (/16)
Characteristics:

✅ Free to use
✅ More secure (hidden from internet)
✅ Unlimited within your network
❌ Can't directly access internet
Use Cases:

Internal servers
Databases
Backend applications
Office computers
AWS Private IPs:

Every EC2 instance gets one
Stays with instance until terminated
Free (included)
Used for internal communication
🔄 How They Work Together:Scenario: Web application in AWS
User (Internet) 
    ↓
Public IP (Web Server: 54.123.45.67)
    ↓
Private IP (Web Server: 10.0.1.10)
    ↓
Private IP (Database: 10.0.2.20)

Users access public IP
Web server talks to database using private IPs
Database never exposed to internet
🔄 Dynamic and Static IPs⚡ Dynamic IP Addresses:What is it? 🎲

Changes each time device connects
Assigned temporarily by DHCP server
Like a hotel room number (changes each visit)
DHCP (Dynamic Host Configuration Protocol) 🤖

Automatically assigns IPs
Manages IP pool
Leases IPs for limited time
Renews when expired
Advantages: ✅

Easier to manage (automatic)
No manual configuration
Efficient use of available IPs
Cheaper
Disadvantages: ❌

IP changes over time
Hard to find specific device
Not good for servers
DNS records become outdated
Use Cases:

Home internet connections
Office computers
Mobile devices
Most client devices
In AWS:

EC2 instances get dynamic public IP by default
IP released when instance stops
New IP assigned when restarted
Free (no extra charge)
📌 Static IP Addresses:What is it? 🎯

Never changes
Manually assigned
Always the same address
Like your permanent home address
Advantages: ✅

Predictable and reliable
Easy to find services
Good for servers
DNS stays correct
Remote access works consistently
Disadvantages: ❌

Manual configuration needed
Uses IPs even when not active
More expensive
Administrative overhead
Use Cases:

Web servers
Email servers
VPN endpoints
Printers in office
CCTV cameras
Remote access systems
In AWS - Elastic IP (EIP): 🎯

Static public IPv4 address
Stays yours until you release it
Can reassign to different instances
Important: Charged if NOT attached to running instance! 💰
Free when attached to running EC2
Limit: 5 per region (can request more)
How to use Elastic IP:

Allocate EIP from AWS
Associate with EC2 instance
Instance now has static public IP
Release when no longer needed
🆚 Comparison:FeatureDynamic IPStatic IPChangesYes, frequentlyNo, permanentCostFree/CheapMore expensiveSetupAutomaticManualBest forClientsServersAWSDefault public IPElastic IP🔧 Troubleshooting Commands🐧 Linux/Mac Network Commands:1. ping 🏓

Tests if host is reachable
Measures round-trip time
Uses ICMP protocol

bashping google.com
ping 8.8.8.8
ping -c 4 192.168.1.1  # Send 4 packets only

Output: Time in ms (lower = better)
If fails: Host down or blocking ICMP
2. ifconfig / ip addr 📡

Shows network interfaces
Displays IP addresses
Shows MAC addresses

bashifconfig              # Older command
ip addr show          # Modern command
ip a                  # Short version

Look for: inet (IPv4), inet6 (IPv6)
3. traceroute / tracepath 🗺️

Shows path to destination
Lists all routers along the way
Identifies where delays occur

bashtraceroute google.com
tracepath google.com    # Doesn't need sudo

Each line = one hop (router)
* * * = router not responding
4. netstat 📊

Shows active connections
Lists listening ports
Displays routing table

bashnetstat -tuln         # TCP/UDP listening ports
netstat -rn           # Routing table
netstat -an           # All connections5. ss ⚡

Modern replacement for netstat
Faster and more detailed

bashss -tuln              # Listening ports
ss -s                 # Summary statistics
ss -t                 # TCP connections6. nslookup / dig 🔍

DNS lookup tools
Converts domain to IP
Tests DNS resolution

bashnslookup google.com
dig google.com
dig google.com +short   # Just the IP7. route 🛣️

Shows routing table
Displays gateway

bashroute -n              # Numeric format
ip route show         # Modern version8. curl / wget 📥

Tests HTTP connections
Downloads files

bashcurl https://google.com
curl -I https://google.com    # Headers only
wget https://example.com/file.zip9. telnet 📞

Tests if port is open
Basic connection test

bashtelnet google.com 80
telnet 192.168.1.1 22

Connected: Port is open ✅
Connection refused: Port closed ❌
10. tcpdump 📦

Captures network packets
Analyzes traffic
Requires root access

bashsudo tcpdump -i eth0           # Capture on eth0
sudo tcpdump port 80           # Only HTTP traffic
sudo tcpdump host 192.168.1.1  # Specific host🔍 Troubleshooting Networks🎯 Systematic Troubleshooting Approach:Step 1: Define the Problem 📝

What's not working?
When did it start?
What changed recently?
Is it one device or all devices?
Step 2: Check Physical Layer 🔌

Cables plugged in? ✅
Lights blinking on router/switch? 💡
WiFi enabled? 📶
Device powered on? ⚡
Step 3: Check IP Configuration 🏷️
baship addr show          # Check if IP assigned
ip route show         # Check default gateway

Do you have an IP? (Not 169.254.x.x)
Is subnet mask correct?
Is gateway configured?
Step 4: Test Local Connectivity 🏠
bashping 127.0.0.1        # Test your own machine
ping 192.168.1.1      # Test gateway/router
ping 192.168.1.x      # Test other local device

Success: Local network is working ✅
Fail: Check cables, switch, IP config ❌
Step 5: Test Gateway 🚪
bashping 192.168.1.1      # Ping your router
traceroute 8.8.8.8    # See if packets leave network

Success: Router is reachable ✅
Fail: Router down or misconfigured ❌
Step 6: Test Internet 🌍
bashping 8.8.8.8          # Google DNS (IP-based)
ping google.com       # Domain-based

8.8.8.8 works, google.com fails: DNS problem 🔍
Both fail: No internet connection 🚫
Step 7: Test DNS 🔍
bashnslookup google.com
dig google.com
cat /etc/resolv.conf  # Check DNS servers

Shows which DNS server you're using
Try alternate: 8.8.8.8 (Google) or 1.1.1.1 (Cloudflare)
🚨 Common Network Problems & Solutions:Problem 1: No Internet Connection 🚫

✅ Check cable/WiFi connection
✅ Restart router and device
✅ Check IP address: ip addr
✅ Ping gateway: ping 192.168.1.1
✅ Ping internet: ping 8.8.8.8
✅ Check firewall settings
  else
    echo "Minor"
  fi

Loops:

bash  for i in 1 2 3 4 5; do
    echo "Number $i"
  done

Functions:

bash  greet() {
    echo "Hello $1"
  }
  greet "World"

User input: read -p "Enter name: " NAME
Arguments: $1, $2, $3 (first, second, third argument passed to script)


🎓 Quick Tips

✅ Use sudo for admin tasks (super user do)
✅ Be careful with rm - files are gone forever!
✅ Use Tab for auto-complete - saves time!
✅ Read error messages - they tell you what's wrong
✅ Practice makes perfect - keep typing commands!


