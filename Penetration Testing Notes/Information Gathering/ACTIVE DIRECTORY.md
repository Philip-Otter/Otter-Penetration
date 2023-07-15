---
tags: Active_Directory, Windows, Kerberos, GUID, LDAP, MSRPC, SAM, NTDS.dat, Hashing, User_Privileges, Passwords, NTLM
---
# ADFS (Active Directory Federation Service)
***
	This allows for SSO within the environment.
	Uses client based access control

# Distinguished Name (DN)
***
	The full path to an AD object
	Must be unique

# Domain Controller
***
## How to Locate
***
	Can look for an open port 88 because Kerberos uses that port
# Flexible Single Master Operation Roles (FSMO Roles)
***
## Five Roles
***
### Schema Master
- One per forest
### Domain Naming Master
- One per forest
### Relative ID Master
- One per domain
### Primary Domain Controller Emulator
- One per domain
### Infrastructure Master
- One per domain
### All five roles are assigned to the first DC in the forest
##### Each time a new domain is added only the RID master PDC emulator and infrastructure master roles are assigned
# Foreign Security Principal (FSP)
***
	Object that represents a security principal that belongs to a trusted external forest
	Created when an external object is added to a group in the current domain
	Holds the SID of the foreign object
## Location
***
	In a specific container called Foreign Security Principals
# Global Catalog (GC)
***
	A feature that can be enabled on a Domain Controller
## Domain controller that stores a copy of all objects in an AD forest
***
	Keeps a full copy of objects in the current domain
	Keeps a partial copy of objects that belong to other domains
	Standard DCs keep a full copy of **only** what is in their own domain
	Performs Authentication
	Performs Object Search
		Allows object search to extend to all domains within a forest

# Group Policy Object (GPO)
***
	Virtual collections of policy settings
	Has a unique GUID
# GUID (Global Unique Identifier)
***
	A unique 128-bit value
	Assigned when a domain user or group  is created
	Used by AD to identify objects internally

# Kerberos
***
	Default AD authentication program since Windows 2000
	Is an open standard
	Stateless Authentication
		Depends on tickets being sent rather than passwords
## Mutual Authentication
***
	Both the user and the server verify their identity

## Kerberos Key Distribution Center (KDC)
***
	Found on a Domain Controller
	Responsible for issuing tickets
	Does not record previous interactions
		Relies on valid TGT
			Assumes that if there is a valid TGT then the user has verified their identity

## Kerberos Process
***
1. User logs on
	1. Password converted to NTLM hash
		1. Used to encrypt the TGT
2. KDC on the DC checks the authentication request
	1. AS-REQ
	2. Verifies user information
		1. Creates a TGT that is sent to the user
3. User presents TGT to DC
	1. Requests a TGS ticket for a specific service
		1. Ticket Granting Service ticket
		2. TGS-REQ
		3. If TGT is validated its data is copied over to create the TGS ticket
4. TGS is encrypted with NTLM password hash of the service or computer account in whose context the service instance is running
	1. Delivered in TGS-REP
5. User presents TGS to the service 
	1. If valid access is granted 
	2. AP-REQ

# LDAP
***
	Open source cross platform protocol
	Used for authenticating various directory services
	How systems in the network can speak in AD
	Sent in cleartext by default
# Leaf Objects
***
	Objects that are unable to house other objects
## Contact object
***
	Type of leaf object
	Represents an external user
	No SID only GUID
		Not a security principal

# Microsoft Remote Procedure Call (MSRPC)
***
	Windows systems use to access systems in AD
## Four Key Interfaces 
- LSARPC
	- A set of RPC calls to the local security authority system (LSA)
	- LSA
		- Provides interactive authentication services
		- Manages the local security policy on a computer
		- Controls the audit policy
- Netlogon
	- Windows Process to authenticate users and other services in the domain
	- Continually runs in the background
- SAMR
	- Remote SAM
		- Security Accounts Manager
		- Pentesters use to perform recon about the domain
		- By default all users can make SAM queries
- DRSUAPI
	- Microsoft API that implements the DRS remote protocol
		- Directory Replication Service (DRS)
			- Attackers can use this to create a copy of the NTDS.dit
# NTDS.dit file
***
	The heart of AD
## Location
***
### Housed on the DC
- C:\Windows\NTDS\
## What's In It
***
### Stores AD info
#### Password hashes for all users in the domain
- If "store password with reversible encryption" is enabled NTDS.dit will also store them in clear text
# Relative Distinguished Name (RDN)
***
	A single component of the DN
	AD does not allow two objects to share a RDN under the same parent container
		Can have two of the same RDNs in a domain if they have different DNs

# Read Only Domain Controller (RODC)
***
	Read only AD database
	Doesn't cache AD account passwords
		Only exceptions are RODC computer account and KRBTGT passwords
	Includes a read only DNS server
	
# sAMAccountName
	User's logon name

# Service Principal Name
***
	Uniquely identifies a service
	Used by Kerberos to associate an instance of a service with a logon object
# Things To Understand
***
	AD is designed to be backwards compatible so many features are not secure by default
		This is good news for us as the attacker
	Essentially any member connected to the domain can read the whole database regardless of privlage level
		This is good because it leaves us with a wide open path to begin enumerating the environment.


# Trusts
***
	Use to establish forest-forest or domain-domain authentication
		Creates a link between the two authentication systems
## Trust Types
***
### Parent-Child
	Domains within the same forest
	Child has two way transitive trust with the parent domain
### Cross-Link
	Trust between child domains to speed up authentication
### External 
	Non-Transitivie trust
	Between two seperate domains in two seperate forests
		Not already joined by a trust
	Uses SID filtering
### Forest
	Transitive trust between two forest root domains
	Tree-root
		Two way transitive trust
		Between a forest root domain and a new tree root domain
## Transitive VS Non-Transitive Trusts
***
### Transitive
- Trust is expanded to objects the child-domain trusts
### Non-Transitive
- Only the child domain is trusted

## Bidirectional VS One-Way Trusts
***
- Bidirectional
	- Users from both domains can access resources in a trusting domain
- One-Way
	- Only users in a trusted domain can access resources in a trusting domain
	- Direction of trust is opposite to the direction of access
# Tombstone
***
	Container that holds deleted objects
	Default AD delete time is 180 days
# User Principal Name (UPN)
***
	An identifier for AD users
		uses account name + the domain name
			philip@2xdropout.xyz

