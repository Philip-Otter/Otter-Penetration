# ADFS (Active Directory Federation Service)
***
	This allows for SSO within the environment.
	Uses client based access control

# Distinguished Name (DN)
***
	The full path to an AD object
	Must be unique

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


# User Principal Name (UPN)
***
	An identifier for AD users
		uses account name + the domain name
			philip@2xdropout.xyz

