---
layout: post
title: "UFW"
date: 2023-09-05  
---

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
