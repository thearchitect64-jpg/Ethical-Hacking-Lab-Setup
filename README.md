# Ethical-Hacking-Lab-Setup
Week 1 of CyberSecurity Internship w/ Networkwalks


# Cybersecurity Lab - Phase 1

## Project Overview

This project is the first phase of my cybersecurity lab setup. The goal was to create a safe virtual environment where I can practice cybersecurity and ethical hacking without affecting my personal computer or other networks.

I used VirtualBox to create the virtual lab and installed Kali Linux 2026.2 ARM64 as my security testing machine.

## Lab Goals

The main goals for Phase 1 were:

- Install VirtualBox
- Create a private virtual network
- Install Kali Linux 2026.2 ARM64
- Configure Kali's network settings
- Verify Internet and DNS connectivity
- Create a clean snapshot of the Kali VM

## My Lab Environment

| Component | Configuration |
|---|---|
| Host Computer | MacBook with Apple Silicon |
| Virtualization Software | Oracle VirtualBox 7.2.16 |
| Security VM | Kali Linux 2026.2 ARM64 |
| Kali RAM | 2048 MB |
| Network Type | NAT Network |
| Network Name | Ethical Hacking Lab |
| Network | 10.0.0.0/24 |
| Kali IP Address | 10.0.0.4/24 |
| Default Gateway | 10.0.0.1 |
| DNS | 8.8.8.8 |

## Lab Network

The lab uses a private NAT Network with the following configuration:

```text
Network Name: Ethical Hacking Lab
Network:      10.0.0.0/24
Gateway:      10.0.0.1
DHCP:         Enabled
IPv6:         Disabled
```

**Step 1** - Install VirtualBox
I installed Oracle VirtualBox 7.2.16 on my MacBook.
VirtualBox is being used to create and manage the virtual machines used in this cybersecurity lab.


**Step 2** - Create the Private NAT Network
I created a custom NAT Network in VirtualBox called:
Ethical Hacking Lab
The network uses:
10.0.0.0/24
This provides a private network for the cybersecurity lab.


**Step 3** - Install Kali Linux
I downloaded Kali Linux 2026.2 ARM64 and created the Kali virtual machine in VirtualBox.
The Kali VM was configured with:
```
RAM:           2048 MB
Network:       Ethical Hacking Lab
Adapter Type:  Intel PRO/1000 MT Desktop
```

**Step 4** - Configure Kali Networking
I verified the Kali network configuration using:

```
ip addr
```
The Kali VM received the following address:
```
10.0.0.4/24
  I also checked the routing table:
ip route
  Default Gateway:
10.0.0.1
```
I tested the connection to the virtual network gateway / internet connectivity / DNS resolution
```
ping -c 4 10.0.0.1
  ping -c 1 1.1.1
    ping -c 4 google.com
```
These tests helped confirm that the Kali VM was able to communicate with the gateway, reach the Internet, and resolve domain names.


**Step 6** - Take a Clean Snapshot
After completing the initial Kali configuration, I created a VirtualBox snapshot.
```
Snapshot Name : CleanKali 2026.2
```
The snapshot provides a recovery point. If I make a mistake during later cybersecurity exercises, I can restore the VM to this clean setup.


**Problems I Encountered**

**Problem 1** **- Kali Internet Connectivity**

At one point, Kali could reach IP addresses but had problems resolving domain names.
I checked the DNS configuration with:
```
 cat /etc/resolv.conf
```

**Problem 2 - Kali GUI**

The Kali installation initially started in a terminal environment instead of the graphical desktop.
I checked the LightDM service with:
```
 systemctl status lighted
```
The LightDM service was running, but the graphical desktop was not initially displayed.
I corrected the LightDM configuration and eventually got the Kali graphical desktop working by changing the Graphics Controller under Display Setting from QemuRamFB > VMSVGA


**Problem 3 - VirtualBox Networking**

I also had to troubleshoot the VirtualBox NAT Network configuration to make sure Kali was using the correct custom network.
The final working configuration was:
```
Ethical Hacking Lab
10.0.0.0/24
Kali IP: 10.0.0.4
```
W**hat I Learned**

During Phase 1, I learned how to:
-Create a virtual machine using VirtualBox
-Create a private NAT Network
-Configure IPv4 networking in Kali Linux
-Check IP addresses and routing tables
-Troubleshoot DNS problems
-Check Linux services using systemctl
-Configure and troubleshoot a graphical Linux desktop
-Create VM snapshots for recovery
-I also learned that troubleshooting a virtual environment can require checking several layers, including the VM settings, network configuration, DNS configuration, and Linux services.

**Security and Ethical Use**

This lab is intended for cybersecurity education and authorized testing only.
Any scanning, vulnerability testing, or exploitation performed in this environment should only be directed at systems that I own or have permission to test.

**Tools Used**

Oracle VirtualBox 7.2.16
Kali Linux 2026.2 ARM64
NetworkManager
LightDM
Linux command line tools
GitHub

**Phase 1 Status**

 VirtualBox installed
 NAT Network created
 Kali Linux installed
 Kali network configured
 Network connectivity tested
 Kali GUI configured
 Clean snapshot created





