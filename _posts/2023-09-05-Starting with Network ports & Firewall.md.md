---
layout: post
title: "Starting with Network ports & Firewall"
date: 2023-09-05  
---

### Starting with Network ports & Firewall !

**Network Ports**

>understanding and managing network ports is crucial for protecting your system from unauthorized access and cyber 
threats. Properly configured ports and firewalls help prevent malicious actors from exploiting vulnerabilities and 
gaining access to your network or sensitive data. In essence, they act as a barrier between your system and potential 
security risks.


| **Service**                          | **Port Number** | **Purpose**                            |
|--------------------------------------|-----------------|---------------------------------------|
| **FTP-DATA**                         | 20              | FTP data transfer                      |
| **FTP (File Transfer Protocol)**     | 21              | File transfer (unencrypted)           |
| **SSH (Secure Shell)**               | 22              | Secure remote terminal access         |
| **Telnet**                           | 23              | Remote terminal access                |
| **SMTP (Simple Mail Transfer Protocol)** | 25           | Sending email (outgoing mail server)  |
| **DNS (Domain Name System)**         | 53              | Resolves domain names to IPs          |
| **HTTP (Hypertext Transfer Protocol)** | 80              | Web pages (for web research)          |
| **HTTPS (HTTP Secure)**              | 443             | Encrypted web pages (for secure web research) |



>know these essential network ports if you want a cheat sheet it's [here](ports.md)


**Firewall Configuring for Arch-linux**

> An uncomplicated Firewall (UFW) is 
a security tool that can help protect 
your computer from network traffic 
and block malicious software from 
accessing your network via the 
internet. To set up a firewall 

`sudo pacman -S ufw`

`sudo systemctl enable ufw`

`sudo systemctl start ufw`

UFW allows you to have full control 
over enabling and disabling ports. 
For example, if you're running an SSH 
server on port 22, you can disable 
this port to prevent connections from 
remote computers.

`sudo ufw deny 22/tcp`


[Read more](UFW.md)