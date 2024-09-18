# Welcome to Microsoft Sentinel Honeypot Security Lab
<img src="https://i.imgur.com/eQ5ykGc.png"/>

## Objective

Today we are going to be setting up Azure Sentinel (SIEM) as well as a Virtual Machine (HoneyPot). The Virtual Machine will be super vulnerable to the internet, We will essentially monitor and Log the RDP Attacks form the different countries. 

This lab was designed to showcase my experience with Azure Sentinel (SIEM) and creating a Honeypot. 

### Skills Learned
- Exposure to Microsoft Sentinel SIEM, capabilities and practical application.
- Log transformation

### Tools Used
- (Snort, Suricata, PfBlockNG) Security Information and Event Management (SIEM) system log ingestion, Analysis and Blocking Malicious IPs.
- Network analysis tools (Wireshark, Advanced IP Scanner) for capturing and examining network traffic.
- Network Documentation (Packet Tracer, GitHub)
- Firewall tool (Pfsense) for protecting the network.
- Cisco Router (csr1000v) for routing packets
- Windows 11 Ent Client for client machines
- Windows 2016 Core Server for DHCP, DNS and WINS IP configurations to client machines as well as Windows Server as a Router
- Windows 2016 GUI Server for managing the network (Router, Firewalls, and computers)

### Features
- VPN that is setup to be Point-to-Point.
- Active Directory Domain Service (Forest and Child Domain), Redundant Domain Controllers for Authentication, Authorization and Availability. 
- Pfsense Firewall and created Firewall Rules, blocking unnecessary ports.
- Routing rules Blocking specific Ip Addresses.
- Hyper-V Virtualization using Virtual Network Adapters to connect all Virtual Machines in this lab.

### Resources
https://techgiovanni1.imgur.com/all
