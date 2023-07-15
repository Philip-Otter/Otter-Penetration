---
Tags: SMTP, Nmap, Automated_Tools, Email
---
# Commands
***
- AUTH PLAIN
- HELO
	- Log in
- MAIL FROM
	- Client names the sender
- RCPT TO
	- Client names recipient
- DATA
	- Client initiates the transmission of the email
- RSET
	- Aborts transmission
	- Keeps client-server connection
- VRFY
	- Checks if a mailbox is available for message transfer
- EXPN
	- Checks if a mailbox is available for messaging
- NOOP
	- Request a server response
	- Prevents disconnection due to timeout
- QUIT

# Footprinting
***
## Nmap
***
### `sudo nmap {targetIP} -p {port} --script smtp-open-relay`
## smtp-user-enum
***
### `smtp-user-enum -U {wordList} -t {hostIP} -p {port}`
- if confident that at least one user in your list is valid and the results came back with not hits then increase your timeout with -w
- -m
	- set the worker processes
# How It Works
***
	Connections are made via telnet
		Ports 25 and 587