
# Windows Active Directory Lab

A hands-on Windows Active Directory lab with the goal of exploring and implementing an Active Directory environment.

In this project we will be setting up and configuring a Windows Active Directory server as a Domain Controller also called DC and as a DNS server. We will also be adding a Windows 11 machine and login as a user to replicate how a machine would be enrolled to Active directory in a real world environment.

## Lab Architecture

- **Domain Controller:** Windows Server 2025 (`DC01`)
- **Client Machine:** Windows 11 (`WIN01`)
- **Domain:** `lab.internal`
- **Virtualization:** VMware Workstation
- **Network:** Static IP configuration and DC+DNS resolution

## Documentation

1. [[Setting up the VMs]]
   - Downloading Windows evaluation images
   - Creating and configuring virtual machines

2. [[Deployment and initial configuration]]
   - Initial Windows Server configuration
   - [[Set static IP for DNS]]
   - Configuring DNS
   - Installing Active Directory Domain Services
   - Promoting the server to a domain controller

3. [[Setting Up OUs, Users, and Groups]]
   - Creating Organizational Units (OUs)
   - Creating domain users and groups.
   - Creating Group Policy Objects(GPOs)

4. [[Joining a client machine to domain]]
   - Configuring client DNS settings
   - Joining Windows 11 to `lab.internal`
   - Testing login

5. [[Basic Administration]]
   - Managing domain user accounts
   - Troubleshooting password expiration and authentication
   - Testing network connectivity and remote management
   - Configuring Windows Firewall rules

6.  [[Lab Architecture and Conclusion]]
   - Network topology
   - Configuration summary
   - Lessons learned and future improvements

## Project Objectives

- Understand AD DC and configurations
- Implement a Domain Control server
- Configure and setup DNS for AD DNS server.
- To gain practical/hands-on experience on administrating an AD server.


## Future Improvements

- File server and NTFS permissions
- PowerShell-based mass user enrollment
- Windows LAPS
- Centralized event logging and auditing






