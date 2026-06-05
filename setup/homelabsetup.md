# pfSense Home Lab Setup #


# Overview
This project documents the creation of a virtualized home lab environment using pfSense as a firewall and router. The objective was to simulate a small enterprise network for learning network security, firewall configuration, traffic analysis, vulnerability assessment, and penetration testing in a safe and isolated environment.


# Objectives
* Deploy pfSense as a virtual firewall.
* Create separate WAN and LAN networks.
* Connect client machines through the pfSense firewall.
* Provide internet access to internal hosts.
* Prepare an environment for cybersecurity and networking labs.


## Lab Architecture
Internet
↓
WAN Interface
↓
pfSense Firewall
↓
LAN Interface
↓
Internal Virtual Network
├── Kali Linux (Attacker Machine)
├── Ubuntu Server/Desktop
└── Additional Test Machines


## Technologies Used

* Oracle VirtualBox:                https://www.virtualbox.org/wiki/Downloads 
* pfSense Community Edition         https://archive.org/download/pfSense-CE-2.6.0-RELEASE-amd64 (Download the iso file)
* Kali Linux                        https://www.kali.org/get-kali/#kali-platforms
* Ubuntu Linux                      https://ubuntu.com/download/desktop


## Virtual Machine Configuration

### pfSense

Adapter 1 (WAN)
* Mode: Bridged Adapter
* Purpose: Internet Connectivity
![alt text](/Adapter1.png)

Adapter 2 (LAN)
* Mode: Internal Network
* Network Name: LabNet
![alt text](/Adapter2.png)



### Kali Linux
Adapter 1
* Mode: Internal Network
* Network Name: LabNet
![alt text](/KaliAdapter1.png)


### Ubuntu
Adapter 1
* Mode: Internal Network
* Network Name: LabNet
![alt text](/UbuntuAdapter1.png)


## Network Configuration

### WAN Interface

* Obtains IP address from home router via DHCP.
* Provides internet connectivity to the lab.

### LAN Interface

* Default Gateway: pfSense LAN Interface
* DHCP Server Enabled
* Internal clients receive IP addresses automatically.


## Deployment Process

### Step 1: Install pfSense

* Downloaded pfSense ISO.
* Created a VirtualBox VM.
* Attached pfSense installation media.
* Completed installation and rebooted.
![alt text](/pfSense.png)
Help Video: https://www.youtube.com/playlist?list=PL9Puyn_9KBpjmpB91oxl-j6_IM1mRsWLp

### Step 2: Configure Interfaces

Assigned interfaces:
WAN → Adapter 1
LAN → Adapter 2

Verified interface assignment through the pfSense console menu.

### Step 3: Configure LAN

Assigned LAN IP address.

Example:
10.0.0.1/24
Enabled DHCP server for automatic client addressing.

### Step 4: Configure Client Machines

Configured Kali Linux and Ubuntu to connect to the Internal Network.
Verified DHCP lease assignment:
ip addr        

To Verify connectivity:
ping 10.0.0.1
ping google.com

### Step 5: Access pfSense Web Interface

Accessed:

https://10.0.0.1
Completed the setup wizard and configured administrative settings.


### Connectivity Testing

Verified:

* Client to pfSense communication.
* Client to internet communication.
* DNS resolution.
* Routing through pfSense.

Commands used:

ping google.com
traceroute google.com
ip addr

## Security Applications

This lab can be used for:

* Firewall Rule Testing
* Network Segmentation
* Packet Analysis
* Vulnerability Assessment
* Intrusion Detection
* OWASP Testing
* SIEM Integration
* Penetration Testing Practice


## Challenges Encountered

### Interface Assignment Confusion

Initially assigned WAN and LAN adapters incorrectly, causing connectivity issues.

Resolution:

* Reconfigured adapter assignments.
* Verified interface mapping within pfSense.

### DHCP Issues

Client machines initially failed to obtain IP addresses.

Resolution:

* Confirmed Internal Network configuration.
* Verified DHCP server settings in pfSense.


## Lessons Learned

* Understanding WAN and LAN separation.
* Basic firewall deployment and configuration.
* DHCP and DNS troubleshooting.
* Packet capture and analysis fundamentals.
* Network segmentation concepts.
* Virtualized lab design principles.


## Conclusion
This project successfully created a functional pfSense-based home lab capable of supporting networking and cybersecurity experiments. The environment provides a safe platform for learning firewall administration, network monitoring, traffic analysis, and offensive security techniques.
