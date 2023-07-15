---
tags: IPMI, Nmap, MetaSploit
---
	Intelliget Platform Management Interface
		A set of standardized specifications for hardware based host management systems
			These hardware based host management devices are autonomous subsystems that are independant from the host's BIOS, CPU, firmware, and OS
				This allows for management and monitoring even while offline
# Footprinting
***
## MetaSploit
***
### search for `.../ipmi/ipmi.version`
## Nmap
***
### `sudo nmap -sU --script ipmi-version - p {port} {target}`
# How It Works
***
	Communicates over UDP port 623
		Many of these devices also exposes a web console and a remote access command line protocol
