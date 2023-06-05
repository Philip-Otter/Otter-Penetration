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
# HTTPS
***
	Can utilize either TLS or SSL.
	Uses ports 443 and 8443

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