📝 WEEK 3

LINUX,NETWORKING

Computers connected together to share information Like a highway system for data 🚗 Allows devices to communicate 🔑 Key Terms:Network 🕸️

Group of connected devices Share resources and data Protocol 📋

Rules for communication Like a common language computers speak Example: HTTP, TCP/IP, FTP Bandwidth 🚀

Speed of data transfer Measured in Mbps or Gbps Like width of a highway (more lanes = faster) Latency ⏱️

Delay in communication Measured in milliseconds (ms) Lower is better (faster response) Router 🔀

Directs traffic between networks Like a traffic cop Connects your home to the internet Switch 🔄

Connects devices within same network Like a distribution center Sends data to correct device Firewall 🔥🧱

Security barrier Blocks unwanted traffic Protects your network 📊 Network Types: LAN (Local Area Network) 🏠

Small area (home, office) Fast and secure Example: Your home WiFi

WAN (Wide Area Network) 🌍

Large area (cities, countries) Connects multiple LANs Example: The Internet

VPN (Virtual Private Network) 🔐

Secure connection over internet Encrypts your data Like a private tunnel

🎯 OSI Model (7 Layers): Think of it like a mail delivery system 📬 Physical 🔌 → Cables, WiFi signals (the truck) Data Link 📡 → MAC addresses, switches (local delivery) Network 🗺️ → IP addresses, routers (route planning) Transport 🚚 → TCP/UDP, ports (delivery tracking) Session 🤝 → Maintains connections (meeting appointment) Presentation 🎨 → Encryption, formatting (wrapping the package) Application 📱 → HTTP, FTP, email (the actual letter) 🔌 TCP vs UDP:TCP (Transmission Control Protocol) 📦✅

Reliable delivery Checks if data arrived Slower but accurate Example: Web browsing, email UDP (User Datagram Protocol) 📦⚡

Fast delivery Doesn't check if data arrived Faster but can lose data Example: Video calls, gaming, streaming 🏷️ IP AddressesWhat is an IP Address?

Unique address for each device on network Like a home address for computers 🏠 Allows devices to find each other 📍 IPv4 (Version 4):

Most common format Looks like: 192.168.1.100 Four numbers (0-255) separated by dots About 4.3 billion possible addresses Running out of addresses 😰 📍 IPv6 (Version 6):

Newer format Looks like: 2001:0db8:85a3:0000:0000:8a2e:0370:7334 Uses letters and numbers 340 undecillion addresses (almost unlimited!) Slowly replacing IPv4 🎭 IP Address Classes (IPv4):Class A 🏢

Range: 1.0.0.0 to 126.255.255.255 For huge networks (millions of devices) First number identifies network Class B 🏭

Range: 128.0.0.0 to 191.255.255.255 For medium networks (thousands of devices) First two numbers identify network Class C 🏪

Range: 192.0.0.0 to 223.255.255.255 For small networks (254 devices) First three numbers identify network 🔢 Special IP Addresses: 127.0.0.1 → Localhost (your own computer) 🏠 0.0.0.0 → All addresses/any address 255.255.255.255 → Broadcast (send to everyone) 🎯 Subnets & Subnet Masks:Subnet 🗂️

Divides network into smaller sections Improves security and performance Like dividing a building into apartments Subnet Mask 🎭

Identifies which part is network vs device Common: 255.255.255.0 (Class C) Shows how many devices can fit CIDR Notation 📝

Shorter way to write subnet mask Example: 192.168.1.0/24 /24 means first 24 bits are network 🧮 Example:

IP: 192.168.1.10 Subnet: 255.255.255.0 or /24 Network: 192.168.1.0 Usable IPs: 192.168.1.1 to 192.168.1.254 Total devices: 254 ☁️ Networking in AWS🌐 VPC (Virtual Private Cloud):

Your own private network in AWS Like your own data center in the cloud Isolated from other customers Full control over network 🏗️ VPC Components:1. Subnets 🗂️

Sections of your VPC Can be public or private Lives in one Availability Zone Like rooms in your house 2. Internet Gateway (IGW) 🚪🌍

Connects VPC to internet Allows public access Like your front door 3. NAT Gateway 🔄

Allows private subnets to access internet But internet can't access them One-way street for outgoing traffic Costs money 💰 4. Route Tables 🗺️

Directions for network traffic Tells data where to go Each subnet has a route table 5. Network ACLs 🛡️

Firewall at subnet level Stateless (checks both ways) Allow/deny rules by IP 6. Security Groups 🔒

Firewall at instance level Stateful (remembers connections) Only allow rules (no deny) 🎯 Public vs Private Subnets:Public Subnet 🌍

Has route to Internet Gateway Devices get public IPs Accessible from internet Use for: Web servers, load balancers Private Subnet 🔐

No direct internet access Only private IPs More secure Use for: Databases, application servers 📊 Common VPC Setup: VPC (10.0.0.0/16) ├── Public Subnet (10.0.1.0/24) → IGW → Internet │ └── Web Server (public IP) └── Private Subnet (10.0.2.0/24) → NAT → Internet └── Database (private IP only)🌍 AWS Regions & AZs in Networking:

VPC spans entire region Subnets exist in one AZ Best practice: Use multiple AZs for redundancy High availability setup 🌐 Public and Private IP Addresses🔓 Public IP Addresses:What are they? 🌍

Visible on the internet Globally unique Can be accessed from anywhere Like your home's street address Characteristics:

✅ Internet accessible ✅ Routable globally ✅ Must be unique worldwide ❌ Limited supply (expensive) Use Cases:

Web servers Email servers Gaming servers Anything users access directly AWS Public IPs:

Assigned to EC2 in public subnet Can be Elastic IP (static) or auto-assigned (dynamic) Charged if not attached to running instance 🔒 Private IP Addresses:What are they? 🏠

Only visible within private network Not accessible from internet Can be reused in different networks Like an apartment number (only meaningful inside building) Private IP Ranges: (Reserved by IANA)

Class A: 10.0.0.0 to 10.255.255.255 (/8) Class B: 172.16.0.0 to 172.31.255.255 (/12) Class C: 192.168.0.0 to 192.168.255.255 (/16) Characteristics:

✅ Free to use ✅ More secure (hidden from internet) ✅ Unlimited within your network ❌ Can't directly access internet Use Cases:

Internal servers Databases Backend applications Office computers AWS Private IPs:

Every EC2 instance gets one Stays with instance until terminated Free (included) Used for internal communication 🔄 How They Work Together:Scenario: Web application in AWS User (Internet) ↓ Public IP (Web Server: 54.123.45.67) ↓ Private IP (Web Server: 10.0.1.10) ↓ Private IP (Database: 10.0.2.20)

Users access public IP Web server talks to database using private IPs Database never exposed to internet 🔄 Dynamic and Static IPs⚡ Dynamic IP Addresses:What is it? 🎲

Changes each time device connects Assigned temporarily by DHCP server Like a hotel room number (changes each visit) DHCP (Dynamic Host Configuration Protocol) 🤖

Automatically assigns IPs Manages IP pool Leases IPs for limited time Renews when expired Advantages: ✅

Easier to manage (automatic) No manual configuration Efficient use of available IPs Cheaper Disadvantages: ❌

IP changes over time Hard to find specific device Not good for servers DNS records become outdated Use Cases:

Home internet connections Office computers Mobile devices Most client devices In AWS:

EC2 instances get dynamic public IP by default IP released when instance stops New IP assigned when restarted Free (no extra charge) 📌 Static IP Addresses:What is it? 🎯

Never changes Manually assigned Always the same address Like your permanent home address Advantages: ✅

Predictable and reliable Easy to find services Good for servers DNS stays correct Remote access works consistently Disadvantages: ❌

Manual configuration needed Uses IPs even when not active More expensive Administrative overhead Use Cases:

Web servers Email servers VPN endpoints Printers in office CCTV cameras Remote access systems In AWS - Elastic IP (EIP): 🎯

Static public IPv4 address Stays yours until you release it Can reassign to different instances Important: Charged if NOT attached to running instance! 💰 Free when attached to running EC2 Limit: 5 per region (can request more) How to use Elastic IP:

Allocate EIP from AWS Associate with EC2 instance Instance now has static public IP Release when no longer needed 🆚 Comparison:FeatureDynamic IPStatic IPChangesYes, frequentlyNo, permanentCostFree/CheapMore expensiveSetupAutomaticManualBest forClientsServersAWSDefault public IPElastic IP🔧 Troubleshooting Commands🐧 Linux/Mac Network Commands:1. ping 🏓

Tests if host is reachable Measures round-trip time Uses ICMP protocol

bashping google.com ping 8.8.8.8 ping -c 4 192.168.1.1 # Send 4 packets only

Output: Time in ms (lower = better) If fails: Host down or blocking ICMP 2. ifconfig / ip addr 📡

Shows network interfaces Displays IP addresses Shows MAC addresses

bashifconfig # Older command ip addr show # Modern command ip a # Short version

Look for: inet (IPv4), inet6 (IPv6) 3. traceroute / tracepath 🗺️

Shows path to destination Lists all routers along the way Identifies where delays occur

bashtraceroute google.com tracepath google.com # Doesn't need sudo

Each line = one hop (router)

= router not responding
netstat 📊
Shows active connections Lists listening ports Displays routing table

bashnetstat -tuln # TCP/UDP listening ports netstat -rn # Routing table netstat -an # All connections5. ss ⚡

Modern replacement for netstat Faster and more detailed

bashss -tuln # Listening ports ss -s # Summary statistics ss -t # TCP connections6. nslookup / dig 🔍

DNS lookup tools Converts domain to IP Tests DNS resolution

bashnslookup google.com dig google.com dig google.com +short # Just the IP7. route 🛣️

Shows routing table Displays gateway

bashroute -n # Numeric format ip route show # Modern version8. curl / wget 📥

Tests HTTP connections Downloads files

bashcurl https://google.com curl -I https://google.com # Headers only wget https://example.com/file.zip9. telnet 📞

Tests if port is open Basic connection test

bashtelnet google.com 80 telnet 192.168.1.1 22

Connected: Port is open ✅ Connection refused: Port closed ❌ 10. tcpdump 📦

Captures network packets Analyzes traffic Requires root access

bashsudo tcpdump -i eth0 # Capture on eth0 sudo tcpdump port 80 # Only HTTP traffic sudo tcpdump host 192.168.1.1 # Specific host🔍 Troubleshooting Networks🎯 Systematic Troubleshooting Approach:Step 1: Define the Problem 📝

What's not working? When did it start? What changed recently? Is it one device or all devices? Step 2: Check Physical Layer 🔌

Cables plugged in? ✅ Lights blinking on router/switch? 💡 WiFi enabled? 📶 Device powered on? ⚡ Step 3: Check IP Configuration 🏷️ baship addr show # Check if IP assigned ip route show # Check default gateway

Do you have an IP? (Not 169.254.x.x) Is subnet mask correct? Is gateway configured? Step 4: Test Local Connectivity 🏠 bashping 127.0.0.1 # Test your own machine ping 192.168.1.1 # Test gateway/router ping 192.168.1.x # Test other local device

Success: Local network is working ✅ Fail: Check cables, switch, IP config ❌ Step 5: Test Gateway 🚪 bashping 192.168.1.1 # Ping your router traceroute 8.8.8.8 # See if packets leave network

Success: Router is reachable ✅ Fail: Router down or misconfigured ❌ Step 6: Test Internet 🌍 bashping 8.8.8.8 # Google DNS (IP-based) ping google.com # Domain-based

8.8.8.8 works, google.com fails: DNS problem 🔍 Both fail: No internet connection 🚫 Step 7: Test DNS 🔍 bashnslookup google.com dig google.com cat /etc/resolv.conf # Check DNS servers

Shows which DNS server you're using Try alternate: 8.8.8.8 (Google) or 1.1.1.1 (Cloudflare) 🚨 Common Network Problems & Solutions:Problem 1: No Internet Connection 🚫

✅ Check cable/WiFi connection ✅ Restart router and device ✅ Check IP address: ip addr ✅ Ping gateway: ping 192.168.1.1 ✅ Ping internet: ping 8.8.8.8 ✅ Check firewall settings else echo "Minor" fi

Loops:

bash for i in 1 2 3 4 5; do echo "Number $i" done

Functions:

bash greet() { echo "Hello $1" } greet "World"

User input: read -p "Enter name: " NAME Arguments: $1, $2, $3 (first, second, third argument passed to script)

🎓 Quick Tips

✅ Use sudo for admin tasks (super user do) ✅ Be careful with rm - files are gone forever! ✅ Use Tab for auto-complete - saves time! ✅ Read error messages - they tell you what's wrong ✅ Practice makes perfect - keep typing commands!

Connect using SSH: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html EC2 Instance Connect: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-connect-methods.html Session Manager (no SSH needed): https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.html
