Host Discovery: 
- use nmap to check whether the host is alive via **ICMP echo requests**

NMap Params: 
- Host Related:
	- 'ip/num' the num defines a network range / *subnet* 
		- this notation is known as 'CIDR' or Classless Inter-Domain Routing
		- /24 scans 256 Addresses
		- /30 scans 4 addresses
	- '-sn' disables port scanning
	- '-oA ---' stores the results in the file name --- 
	- '-iL ---' allows a list of ips to be scanned at once, where the -- arg is a .lst file. Or rather you could just stack multiple ips in a row when scanning eg. sudo nmap -oA res 00.000.0.00 11.111.1.11
- Port Related:
	- '--top-ports=x' where x is the top amount of ports to be scanned
	- '-p' specifies port to scan
	- '-sU' a UDP scan, looks for active udp services running on the target machine. Slower than a regular scan.
	- '-sV' a service scan which provides more data on open ports such as versions, service names and details about the target.
- Tidying:
	- '-n' disables DNS scan
	- 'Pn' disables ICMP echop requests
	- '--disable-arp-ping' self explanatory.

Connect Scan
- '-sT' uses the TCP three=way handshake to determine if a specific port on a taget host is open or closed. By sending a SYN pacjet to the target port and awaiting a response. It is considered open if the targot port responds with an SYN-ACK Packet and closed if it responds with an RST Packet.

Saving Results
- -oN has the normal .nmap output file extension
- -oG with the .gnmap file extension which is grepable to be examined in terminal 
- -oX with the.xml file extension I <3 xml fr
	- wait so cool, you can export to xml via -oX then use the tool xsltproc to create an html report which is easier to read

xsltproc
- eg. xsltproc info.xml -o target.html

Filtered Ports
- ports can show with a few different statuses, a filtered port means it cannot be shown, often due to firewalls having certain rules set to handle specific connections. And this causes the sent packets to be dropped or rejected. 