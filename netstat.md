# netstat command
- netstat is a command-line network utility that displays:
    network connections for TCP, UDP
    routing tables,
    a number of network interface
    network protocol statistics.

# Testing senario
1. sinu not able to connect to webappserver runing on test server on 12345 port number
- he check by ping comand - all ok
- then use netstat command to check check port no. and he found that port is using by other proccess so it use KILL comand and then try again

2. here ping and netstat both fine then
- connect with aplication server team and ask what issue is with application and if it is running on diff port give me its detail  

# CASE 
to identify no. of connection ona given port or ip
- netstat -putan | grep :<port/ip>

# netstat Command Options and Examples
- Options Used:
t - tcp
u - udp
n - numerical addr
l - listening port
p - PID programname

- Examples:
To see all the sockets netstat -a
List all the TCP ports netstat -at
List all the TCP v6 ports netstat -6at
List all the UDP ports netstat -au
List all listening ports netstat -l
To view the numerical address netstat -ln
To view the PID of the programme of connection netstat -p
To view the routing table netstat -r
To check no. of connection from a specific IP netstat -an | grep <IP>
To get the list of all the interface netstat -i
Which port a process is using? netstat -ap | grep <process_name>
How to see statistics by protocol? netstat -s