# SSH 

What is SSH?
Why it is called SSH?
Some basics of SSH * How to use SSH in Linux?
Example of SSH
    Access Linux server using Putty
    Access a Linux server from another server

# What is SSH?
SSH or Secure Shell is a network communication protocol that enables two computers/devices to communicate and share data.

# Why it is called as Secure Shell?
Because communication between host and client will be in encrypted format.

# More about SSH
- The default port for SSH client connections is 22.
- We can change the default port and use one between 1024 and 32,767.
- SSH is also a command in Linux
- It is used to access another Linux server or accessing a Linux server from a terminal.
- Syntax: ssh user_name@host(IP/Domain_name)

# How to use SSH?
- To use SSH, ssh service must be installed on Linux server
You can check using rpm-qa grep ssh, or
check the file /etc/ssh/sshd_config
- If not already installed then install below two install openssh-clients openssh-server
- and now enable the ssh or check if it is enabled using systemct status sshd


# Examples of SSH
- Access Linux server using Putty. (Putty is a common SSH client for Windows).
- Access a Linux server from another server.

