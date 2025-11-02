# Topics
What is a FireWall?
firewalld service in Linux
Enable/disable firewalld
How to see the existing firewall rules?
Adding & Deleting Firewall Rules
Adding/removing ports
Block incoming/outgoing traffic
Block ICMP

# What is a Firewall?
A firewall is a network security system that monitors and controls incoming and outgoing network traffic based on the rules defined.

Basically used to determine and block untrusted network to access out system.


# Types of Firewall?
- Software Based
Running on Operating System
- Hardware Based
A dedicated appliance with Firewall software between two different networks (mostly used by network team)

# Tools on linux for managing firewall
1. iptables
2. firewalld - newer version of centos,Redhat, Fedora etc


# Commands
===========
- Listening, adding deleting firewall rules
Check if firewalld service is installed
Rpm -qa | grabfirewalld
- stop, start firewalld service
Systemctl start/enable firewalld
Stop disable
Staus
Restart
- check the rules for firewall
Firewall-cmd —list-all
- Listing of all the services firewalld is aware of
Firewalld-cmd —get-services
- To reload the configure of firewallD
Firewall-cmd —reload
- firewall has multiple zones to get list
Firewall-cmd —get-zones
- to see the list of active zone
Firewall-cmd —get-active-zone
- to get firewall rules for a specific zone
Firewall-cmd —zone=public —list-all
- to add or remove a service
Firewall-cmd —add/remove-service=nameofservice
- To reload the config
Firewall-cmd —reload
- to add or remove a service permanently
Firewall-cmd —add/remove-service=nameofservice --permanent
- to add remove the port
Firewall-cmd —add/remove-port=20201/tcp
- to block incoming traffic from IP
firewall-cmd --add-rich-rul='rule family="ipv4" source address="192.168.0.0" reject"
- to block outgoing traffic to IP or URL
firewall-cmd --direct --add-rule ipv4 filter OUTPUT 0 -d <ip> -j DROP
- To block ICMP incoming traffic 
firewall-cmd --add-icmp-block-inversion
- 

