---
tags: SNMP, Networking, MIB, Key, Encryption, Passwords, Automated_Tools, Brute_Forcing, OIDs, Nmap
---
	Simple Network Management Protocol
# Footprinting
***
## Braa
***
	Tool for brute forcing OIDs
### `braa {communityString}@{targetIP}`
## nmap
***
	Use the snmpinfo script
## OneSixtyOne
***
	Community string brute forcing tool
### `onesixtyone -c {wordlist} {targetIP}`
### Theory
***
	Organizations will often have a naming pattern. If we can figure it out we can use a tool like crunch to be able to build a custom wordlist
## SNMPwalk
***
	Many snmpcmd flags work with snmpwalk
### `snmpwalk -v {version} -c {communityString} {targetIP} -c Public`
- -c Public
	- provides us with public information
# How It Works
***
	Uses agents that run on UDP 161
	Runs Traps on UDP 162
		Traps send packets from the SNMP server to the client
			These packets were not requested by the client
			Triggers once a specific event happens on the server
## MIB
***
	Management Information Base
	An independent format for storing device information
		Allows devices across manufacturers to work with SNMP
		A text file where all query-able SNMP objects of a device are listed
			Contains at least 1 object identifier
			Written in ASN1
				Abstract Syntax Notation One
			Does not contain data but lists where it is an how to interpret it
### OIDs
***
	Represents a node in a hierarchical namespace
	Consists of integers and usually concatenated by dot notation

# Versions
***
## SNMPv1
***
	No built in authentication
	No built in encryption
## SNMPv2
***
	Two versions
	Community-string has no built in encryption
		Community-strings are like passwords
### SNMPv2
### SNMPv2c
***
	Community based
## SNMPv3
***
	Built in authentication
	Built in encryption
		Encryption is done through the use of a pre-shared key
