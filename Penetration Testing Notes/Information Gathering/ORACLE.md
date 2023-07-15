---
tags: Oracle, Oracle_TNSS, Networking, Apple, Encryption, SID, Brute_Forcing
---
# Connecting
***
## saqplus
***
### `saqplus {username}/{password}@{tagetIP}/XE;`
# Footprinting
***
## SID Brute Forcing
***
	System Identifier
### Nmap
***
#### `nmap ... ... --script=oracle-sid-brute`
# Oracle TNS
***
	Oracle Transparent Network Substrate
		Communications protocol
			Lets Oracle databases and applications talk over the network
	Default listener can be found on TCP port 1521
		Configured to support various network protocols
			TCP/IP
			UDP
			IPX/SPX
			AppleTalk
		Only accepts connections from authorized hosts
		Has basic authentication
		Will use Oracle Net Services to encrypt traffic between client and server
## TNS Config FIles
***
### Files
***
- tnsnames.ora
- listener.ora
### Location
***
	Typically located in `ORACLE_HOME/network/admin`

