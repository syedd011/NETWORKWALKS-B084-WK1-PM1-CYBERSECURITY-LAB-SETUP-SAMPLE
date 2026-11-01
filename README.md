<div align="center">
  
  # Cybersecurity Practice Tools Lab Environment
  
***Building an ethical hacking virtual controlled lab for penetration testing practice***
</div>  
<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ver-Virtualbox%20v7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Virtualization-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-404040?style=flat-square&labelColor=C00000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Waqas%20Karim%20CCIE-C00000?style=flat-square" />
</p>


## OVERVIEW OF PROJECT

This project is developed for practicing and setting up a "virtual lab for cybersecurity and penetration testing using VM box manager and Kali linux.

The main idea of the lab is to make a controlled environment where the tools can be used or implemented. Tools such as network scanning, reconnaissance, security-testings etc.


lab is configured on a private network IPv4 so that additional machines can be added in future for testing or being used as a target machine for legal tests.


## LAB OBJECTIVE
Main objectives are:
-Install and configure VirtualBox.
-Install Kali linux as virtual machine
-Create a private "NAT network" for the lab testing
-Assign a consistent IP address to the Kali VM
-verify network connectivity and DNS resolution.
-take a clean snaphshot of the VM for recovery
-prepare environment for future projects


## Purpose of the Lab

The lab provides an isolated controlled environment for learning cybersecurity through self owned devices and legal testing or R&D.
It can be used for: 
- Port scanning
- Vulnerabilty assessment 
- Packet analysis
- Web security testing
- Security tool experiments
  

## IMPORTANT:
This lab must be used for systems owned by yourself or have explicit permission to test. Do not use the lab or its tools to attack illegal or unauthorized devices/machines. 

## Lab Setup and Architecture

## Step 1: Installing 7-zip
7-Zip was installed to extract the Kali Linux virtual-machine package, which may be distributed as a `.7z` archive.

**Tool:** 7-Zip

## Step 2. Install VirtualBox

VirtualBox was installed as the hypervisor

<img width="973" height="971" alt="image" src="https://github.com/user-attachments/assets/cdb4c23b-3bdf-4303-95f1-71cd8ede1355" />

We click on machines and add the file path of Kali linux. Then you should be able to see something like this: 

<img width="981" height="927" alt="image" src="https://github.com/user-attachments/assets/69247ecd-c33f-4cde-98ac-a6fba8762e03" />

After sucessfuly adding Kali, proceed to the Settings and then to Network in order to setup our isolated lab : 
 
<img width="1156" height="956" alt="image" src="https://github.com/user-attachments/assets/73b1b158-59e5-4c0d-a910-6eeca9521078" />

## Step 3. Create the NAT Network 
Selecting the NAT network from the drop down through "Attached to" and making the "Promiscious mode" to allow all. Make sure the "virtual cable connected" is checked, press OK. 
Configuration:
```text
Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
```

<img width="970" height="971" alt="image" src="https://github.com/user-attachments/assets/9c713361-a3a9-4e91-9114-0fcae5f5fe60" />

## Step 4 : oppen kali

<img width="931" height="705" alt="image" src="https://github.com/user-attachments/assets/d6cba0d6-1fcd-4862-bb77-ce829fafa617" />
A shared folder was also configured for transferring required files between the host operating system and the Kali VM.

## Step 5. Configure the Kali Linux Network

The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

Example configuration:

```text
IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8
```

## Step 6. Create a Clean VM Snapshot

After completing the initial configuration, a VirtualBox snapshot was created.

Example snapshot name: my fresh kali linux

The snapshot represents the clean baseline of the laboratory.

<img width="975" height="505" alt="image" src="https://github.com/user-attachments/assets/8c3a5858-d967-4a6a-970a-0d5923dda68f" />

If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.

# 🐞 Problems Encountered & Solutions
Wired connection status false

During the setup of lab to the DNS ipv4 8.8.8.8 i was unable to find the connection of kali machine to the isolated lab environment. I ran the command: 
```text
sudo nano /etc/NetworkManager/NetworkManager.conf
```
<img width="928" height="707" alt="image" src="https://github.com/user-attachments/assets/7d9e6fd6-6fff-47a7-b6a3-d2ee00c99096" />

<img width="930" height="697" alt="image" src="https://github.com/user-attachments/assets/df516e2c-2f88-404e-aa25-26e54e841ca1" />
Here it shows "managed=false" this shows that the configuration is not done and it shows false, by replacing it with "true" helped me establish the connection. 


<img width="680" height="155" alt="image" src="https://github.com/user-attachments/assets/27f2ba58-c84e-4248-a9f6-3dacabcd32cd" />
The state now shows UP which means the connection is established and is ready to be tested. 
The network connection was then restarted/rebooted and connectivity was tested again. 

# What I Learned
Throughout this project, I learned how to create and configure a virtual environment for cybersecurity practice for isolated labs.

The most important concepts I learned include:

### 1. NAT vs NAT Network

A standard NAT configuration and a NAT Network serve different purposes.

A NAT Network allows multiple VMs connected to the same virtual network to communicate with one another while providing network address translation for external connectivity.

This makes it useful for building a multi-machine cybersecurity laboratory.

### 2. Virtual Machine Networking

I learned how VirtualBox virtual network adapters connect virtual machines to different types of networks and how network configuration affects communication between machines.

### 3. Static IP Configuration

I learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.

### 4. VM Snapshots

I learned that a clean snapshot should be created before performing risky or experimental activities.

This provides a known-good recovery point for future points or tasks.

### 5. Documentation

I learned that documenting commands, configuration, screenshots, problems, and solutions is an important part of a professional cybersecurity project.

## THIS LAB IS INTENDED FOR PRACTICE AND EDUCATION PURPOSES ONLY

#  Tools & Resources

- **7-Zip:** [https://7-zip.org/download.html](https://7-zip.org/download.html)
- **VirtualBox:** [https://virtualbox.org/wiki/Downloads](https://virtualbox.org/wiki/Downloads)
- **Kali Linux:** [https://kali.org/get-kali](https://kali.org/get-kali)
- 
# 👤 Guide

**Waqas Karim**\
Cybersecurity Professional B082

LinkedIn: [https://www.linkedin.com/in/waqaskarim/](https://www.linkedin.com/in/waqaskarim/)
## 📌 Project Information

**Program Name:** Cybersecurity at Networkwalks | **Week:** 01 | **Project:** Cybersecurity & Pentesting Lab Setup | **Repository:** GitHub
