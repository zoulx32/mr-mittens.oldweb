---
layout: post
title: "Arch Arsenal"
date: 2023-09-05  
---

## `Empowering Privacy and Security Enthusiasts`

Welcome to **`Arch Arsenal`**, your comprehensive guide to Knowing your Arch Linux 
system for the ultimate privacy and security experience. In this series, we will explore 
the essential tools, configurations, and practices that empower privacy advocates and 
security enthusiasts on the Arch Linux platform also basics since I just forget things 
i want to come here and catch-up

**`Arch Linux`** has long been the preferred choice of discerning users for its 
unparalleled flexibility and minimalism. But what truly sets it apart is the ability to 
mold it into a fortress of digital defense. Whether you're concerned about safeguarding 
sensitive data, maintaining anonymity, or simply want more control over your computing 
environment, Arch Linux provides the foundation to achieve these goals.

>Whether you're a seasoned Arch Linux user looking to further fortify your fortress or 
someone new to the world of privacy and security, this guide if served its purpose will  enlighten you !


>### [Starting with Network ports & Firewall](#Starting-with-Network-ports-&-Firewall)

-  [Firewall Configuring for Arch-linux](Firewall-Configuring-for-Arch-linux)


<br>



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



>know these essential network ports if you want a cheat sheet it's [here](#Port-Cheat-Sheet)


### Firewall Configuring for Arch-linux

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


[Read more](#UFW)



<br>

### UFW

**In UFW, the rules are typically stored in the /etc/ufw directory.Here's a table 
showing the commonly used rule files and their descriptions:**


| Rule File               | Description                                         |
|-------------------------|---------------------------------------------------- |
| `/etc/ufw/ufw.conf`     | UFW configuration file.                             |
| `/etc/ufw/user.rules`   | User-defined rules added using `ufw` commands.      |
| `/etc/ufw/user6.rules`  | User-defined IPv6 rules added using `ufw` commands. |
| `/etc/ufw/before.rules` | Rules applied before user-defined rules.            |
| `/etc/ufw/before6.rules`| IPv6 rules applied before user-defined rules.       |
| `/etc/ufw/after.rules`  | Rules applied after user-defined rules.             |
| `/etc/ufw/after6.rules` | IPv6 rules applied after user-defined rules.        |


>These files control the behavior of the [Uncomplicated Firewall](https://wiki.archlinux.org/title/Uncomplicated_Firewall) (UFW) on your system. 
The user.rules and user6.rules files are where your custom rules are stored when you add 
rules using the ufw command-line tool. The other files are used for system-wide 
configuration and to apply rules at different stages of the firewall rule processing.
You can edit these files to customize your firewall rules, but it's often recommended to 
use the ufw command-line tool to manage your firewall rules for simplicity and safety.

<br>

### Port Cheat Sheet 

>its too much but serves purpose lol !

| Port Number | Protocol   | Purpose                                             |
|-------------|------------|-----------------------------------------------------|
| 20          | FTP        | File Transfer Protocol - Data                       |
| 21          | FTP        | File Transfer Protocol - Control                    |
| 22          | SSH        | Secure Shell - Secure remote login                  |
| 23          | Telnet     | Telnet - Unencrypted remote login                   |
| 25          | SMTP       | Simple Mail Transfer Protocol - Email               |
| 53          | DNS        | Domain Name System - Resolves domain names to IPs   |
| 67          | DHCP       | Dynamic Host Configuration Protocol - IP assignment |
| 68          | DHCP       | Dynamic Host Configuration Protocol - IP request    |
| 80          | HTTP       | Hypertext Transfer Protocol - Web pages             |
| 110         | POP3       | Post Office Protocol 3 - Retrieve email             |
| 143         | IMAP       | Internet Message Access Protocol - Retrieve email   |
| 443         | HTTPS      | HTTP Secure - Encrypted web pages                   |
| 3306        | MySQL      | MySQL Database Server                               |
| 3389        | RDP        | Remote Desktop Protocol - Windows remote desktop    |
| 5432        | PostgreSQL | PostgreSQL Database Server                          |
| 6660-6669   | IRC        | Internet Relay Chat (IRC)                           |
| 8000-8099   | HTTP Proxy | Common ports for proxy servers                      |
| 9000-9099   | Ephemeral  | Commonly used for application-specific purposes     |
| 27017       | MongoDB    | MongoDB Database Server                             |
