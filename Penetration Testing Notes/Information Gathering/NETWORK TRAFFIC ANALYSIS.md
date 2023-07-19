---
tags: Networking, Web, SMB, Encryption, WireShark, Automated_Tools, Keys, Linux, Windows
---

# FTP
***
	Insecure 
	Uses multiple ports at the same time. (20 & 21)
		20 to transport data
		21 to issue commands and controlling the session
	Uses two different modes
		Active
			default for FTP
			Server is listening for a control command port from the client
				States what port to be used for data transfer
		Passive
			Allows for access to FTP servers behind firwalls, NAT-enabled links, etc
## Commands
***
### USER
### PASS
### PORT
	Changes the port used for data transfer while in active mode
### PASV
	Changes the connection to passive 
### LIST
### SWD
### PWD
### SIZE
### RETR
	Retrieves a file from the server
### QUIT
## Downloading files
***
### use the `get`  command
# HTTPS
***
	Can utilize either TLS or SSL.
	Uses ports 443 and 8443

# ICMP Protocol
***
## (RFC) Request for Comments
***
### https://tools.ietf.org/html/rfc792
# IP Protocol
***
## (RFC) Request for Comments
***
### https://tools.ietf.org/html/rfc791
# Resources & Tools
***
## Common Syntax For Most Tools 
***
### https://www.ibm.com/docs/en/qsip/7.4?topic=queries-berkeley-packet-filters
	Berkeley Packet Filters

# SMB
***
## [[Information Gathering/WINDOWS#Protocols#SMB|READ MORE HERE]]
# TCP
***
## Packet Flags
***
### SYN
### SYN, ACK
### ACK
### FIN
	Signals that the data transfer is finished and the send er is requesting termination of the connection.
	Client acknowledges receipt of of data by sending a FIN, ACK
	Server responds with its own FIN, ACK
	Client finishes off with a FIN
### FIN, ACK
## RFC (Request for Comments)
***
### https://tools.ietf.org/html/rfc793
# TCPdump
***
	Command line packet sniffer
	Windows twin called WinDump
	Can be used through remote connections
## Command Flags
***
- -D
	- Displays available interfaces
- -i
	- Selects an interface to capture from 
- -n
	- Don't resolve hostnames
- -nn
	- Don't resolve hostnames and well-known ports
- -e
	- Grab ethernet header w/ upper-layer data
- -L
	- Line buffer 
	- Allows for sending the output to another command via a pipe
- -A 
	- Show contents in ASCII
- -X
	- Show contents of packets in hex and ASCII
- -XX
	- X and specify ethernet headers
- -c
	- Grab a specific number of packets then quit the program
- -s
	- Defines how much of a packet to grab
- -S
	- Use absolute sequence numbers
	- tcpdump defaults to relative sequence numbers
- -q
	- Print less protocol information
- -r
	- Read from a file
	- ==Syntax:== tcpdump -r {fileName}.pcap
- -w
	- Write into a file
	- ==Syntax:== tcpdump ... -w {fileName}.pcap
## Filters
***
- host
	- show anything with a designated host
- src/dest
	- designates src or dest 
	- works on host or ports
- net
	- show any traffic sourcing from or  to the designated newtork
	- uses "/" notation
- proto
	- Filter for a designated protocol
- port
	- show any traffic to or from the designated port
- less/greater
	- used to look for a packet or protocol option of a specific size
	- <,>
- and
	- combine filters
	- &&
- or 
- not
### [[NETWORK TRAFFIC ANALYSIS#Resources & Tools#Common Syntax For Most Tools#https //www.ibm.com/docs/en/qsip/7.4?topic=queries-berkeley-packet-filters|BPF]]
# TShark
***
## Command Flags
***
- -D
	- List available interfaces to capture from
- -L
	- Will list the link-layer mediums you can capture from
- -i
	- Select an interface to capture from
- -f
	- packet filter during capture
- -c
	- Grab a set number of packets
- - a 
	- Defines an auto-stop condition
		- time
		- file size
		- number of packets
- -r
	- read from file
- -W
	- Write into a file
		- pcapng format
- -P
	- print the packet summary while writing into a file
- -x
	- add HEX and ASCII output
- 1

## Termshark
***
	A text based user interface
	Similar to wireshark but can run right in the terminal
### Download links
#### https://github.com/gcla/termshark
# TLS & SSL
***
## TLS
***
	Takes place after establishing a TCP session
### Handshake
1. Client and server exchange hello messages
2. Client and server exchange cryptographic parameters
3. Client and server exchange x.509 certificates and cryptographic information allowing for sessions authentication
4. Generate a master secret 
5. Client and server issue negotiated security parameters to the record layer
6. Client and server verify that their peer has calculated the same security parameters and that no tampering has occured

# UDP Protocol
***
## (RFC) Request for Comments
***
https://tools.ietf.org/html/rfc768
# Wireshark
***
	Don' forget that Wireshark can extract files from the data streams!
## Useful filters
***
### FTP
- Find all FTP commands
	- ==Filter:==  ftp.request.command

## Adding a key in Wireshark
***
1. Edit
2. Preferences
3. Protocols
4. Select the protocol
	1. Depends on what type of key you are going to be adding
5. Add a new key
6. Fill out all fields
7. Save and refresh