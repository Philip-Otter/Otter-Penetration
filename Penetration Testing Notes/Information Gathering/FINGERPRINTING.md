---
tags: Netcat, cURL, Automated_Tools, Banner_Grabbing, Finger_Printing
---
# Banner Grabbing
***
## nc or netcat
***
- ==Syntax:==  `echo "" | nc -v -n -w 5 {ip} {port}`

## cURL
***
- ==Syntax:==  `curl -s -I {ip}`
	- HTTP Banner
## whatweb
***
- whatweb {url} -a {aggressionLevel}

## wget
***
- wget -q -S {ip}
	- HTTP banner

## Telnet
***
- telnet {ip} {port}
	- Grab telnet banner