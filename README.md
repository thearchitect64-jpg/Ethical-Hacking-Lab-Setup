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




