# Ping work for both linux & window

# what a PING command can do

- Check Network Connectivity (verifying if a host is reachable).
- Check Internet Connection (by pinging a public external address).
- Check Network Interface Card (by pinging the local loopback address, typically $127.0.0.1$).
- Check Latency on network (the time it takes for a packet to travel to the destination and back, known as RTT or Round-Trip Time).
- DNS Resolution (by pinging a hostname, which requires DNS to resolve it to an IP address).


# How PING Command Works
The PING command works by sending data packets (specifically, ICMP - Internet Control Message Protocol Echo Requests) from a client (like a laptop) to a target host (like a server). * The example shown is: ping 192.168.0.0

The slide shows the request being sent and the successful reply:
- Request: PING 192.168.0.0 (192.168.0.0) 56(84) bytes of data
- Reply: 64 bytes from 192.168.0.0: icmp_seq=1 ttl=64 time=0.070 ms
- A key takeaway is the indication of a successful test with "0% packet loss".

or 
- Request: PING 192.168.0.0 (192.168.0.0) 56(84) bytes of data
- Reply: X
- A key takeaway is the indication of a unsuccessful test with "100% /50% packet loss".

# reason for not able to connect
1. Firewall
2. Server is down 
3. network/internet/hardware issue from your computer side
4. 50% packet loss - network traffic

# ping command is also used for DNS resolution

Command           	Description
ping hostname   	Pinging a host using its hostname (requires DNS resolution).
ping IP	            Pinging a host using its IP address.
ping -c 3        	Pings three times only (limits the number of packets).
ping -i 2       	Sets the interval to send packets to 2 seconds.
ping -c 5 -q	   Pings 5 times, but the -q (quiet) flag will only give the summary.
ping -f	          Sends packets as fast as possible to test the network performance 
ping -s 500	       Used to change the size of the packet to 500 bytes.
ping -w 10       	Used to stop printing after 10 seconds (sets a timeout).
ping -D www.google.com	   Also prints the timestamp to remember the time.
ping -a	           Sets the output to be audible (sends a sound on success).

# ping localhost (to check network interace of your own system)
