# Week 3: Linux & Networking

## What is Networking?
**Networking:** Computers connected together to share information. Like a highway system for data 🚗

### Key Benefits:
- Share files and printers
- Access internet resources  
- Communicate via email/chat
- Centralized data storage

## Key Networking Terms

| Term | Description | Analogy |
|------|-------------|---------|
| **Protocol 📋** | Rules for communication | Common language computers speak (HTTP, TCP/IP, FTP) |
| **Bandwidth 🚀** | Speed of data transfer (Mbps/Gbps) | Width of highway - more lanes = faster |
| **Router 🔀** | Directs traffic between networks | Traffic cop connecting your home to internet |
| **Firewall 🔥🧱** | Security barrier | Blocks unwanted traffic and protects your network |

## Network Types

### LAN (Local Area Network) 🏠
- Small area (home, office)
- Fast and secure
- Example: Your WiFi network

### WAN (Wide Area Network) 🌍  
- Large area (cities, countries)
- Connects multiple LANs
- Example: The Internet

### VPN (Virtual Private Network) 🔐
- Secure connection over internet
- Encrypts your data
- Like a private tunnel

## OSI Model (7 Layers)
*Think of it like a mail delivery system 📬*

| Layer | Name | Function | Example |
|-------|------|----------|---------|
| **7** | Application 📱 | HTTP, FTP, email | The actual letter |
| **6** | Presentation 🎨 | Encryption, formatting | Wrapping the package |
| **5** | Session 🤝 | Maintains connections | Meeting appointment |
| **4** | Transport 🚚 | TCP/UDP, ports | Delivery tracking |
| **3** | Network 🗺️ | IP addresses, routers | Route planning |
| **2** | Data Link 📡 | MAC addresses, switches | Local delivery |
| **1** | Physical 🔌 | Cables, WiFi signals | The truck |

## TCP vs UDP

| Feature | TCP 📦✅ | UDP 📦⚡ |
|---------|----------|---------|
| **Reliability** | Reliable delivery | Fast delivery |
| **Checking** | Checks if data arrived | Doesn't check if data arrived |
| **Speed** | Slower but accurate | Faster but can lose data |
| **Use Cases** | Web browsing, email | Video calls, gaming, streaming |

## IP Addresses
**IP Address:** Unique address for each device on network. Like a home address for computers 🏠

### IPv4 (Most Common) 📍

192.168.1.100
```unknown
- Four numbers (0-255)
- About 4.3 billion addresses  
- Running out of addresses 😰

### IPv6 (Newer) 📍
2001:0db8:85a3::7334
```unknown
- Uses letters and numbers
- 340 undecillion addresses
- Slowly replacing IPv4

### Special IP Addresses:
- **127.0.0.1** → Localhost (your own computer) 🏠
- **0.0.0.0** → All addresses/any address
- **255.255.255.255** → Broadcast (send to everyone) 🎯

## Public vs Private IP Addresses

### Public IP 🔓
- Visible on the internet
- Globally unique
- Can be accessed from anywhere
- Like your home's street address
- **Use:** Web servers, email servers

### Private IP 🔒
- Only visible within private network
- Not accessible from internet
- Can be reused in different networks
- Like apartment number inside building
- **Use:** Internal servers, databases

### Private IP Ranges:
- **Class A:** 10.0.0.0 to 10.255.255.255 (/8)
- **Class B:** 172.16.0.0 to 172.31.255.255 (/12)
- **Class C:** 192.168.0.0 to 192.168.255.255 (/16)

## AWS Networking (VPC)
**VPC (Virtual Private Cloud):** Your own private network in AWS. Like your own data center in the cloud.

### VPC Components:
- **Subnets 🗂️** - Sections of your VPC (public/private)
- **Internet Gateway 🚪** - Connects VPC to internet
- **NAT Gateway 🔄** - Private subnet internet access

### Common VPC Setup:

VPC (10.0.0.0/16)
├── Public Subnet (10.0.1.0/24)
│   └── Web Server (public IP)
└── Private Subnet (10.0.2.0/24)
    └── Database (private IP)

## Network Troubleshooting Commands

### Basic Tests:
bash
ping google.com              # Test if host is reachable
traceroute google.com        # Show path to destination  
nslookup google.com          # DNS lookup
### System Info:
bash
ip addr show                 # Show network interfaces
netstat -tuln               # Show listening ports
ss -tuln                    # Modern netstat

## Systematic Network Troubleshooting

### 5-Step Process:

1. **Define the Problem 📝**
   - What's not working? When did it start? What changed recently?

2. **Check Physical Layer 🔌**
   - Cables plugged in? Lights blinking? WiFi enabled?

3. **Test Local Network 🏠**
      ping 127.0.0.1 && ping 192.168.1.1
   4. **Test Internet 🌍**
      ping 8.8.8.8 && ping google.com
   5. **Check DNS 🔍**
   - If IP works but domain doesn't, it's DNS

## Week 3 Key Takeaways 🎯

✅ Networks connect devices to share information  
✅ IP addresses are like home addresses for computers  
✅ TCP is reliable but slower, UDP is fast but can lose data  
✅ Private IPs are for internal networks, public IPs for internet  
✅ VPC creates your private cloud network in AWS  
✅ Public subnets have internet access, private don't  
✅ OSI model has 7 layers from physical to application  
✅ Systematic troubleshooting starts with physical layer  

### Personal Note:
Networking seemed overwhelming at first with all the protocols and addressing schemes. But understanding that it's just like a postal system - addresses, routes, and delivery methods - made everything click. The troubleshooting approach of checking each layer systematically is a game-changer!
