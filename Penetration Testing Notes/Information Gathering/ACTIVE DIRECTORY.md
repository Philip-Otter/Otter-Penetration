# ADFS (Active Directory Federation Service)
***
	This allows for SSO within the environment.
	Uses client based access control

# GUID (Global Unique Identifier)
***
	A unique 128-bit value
	Assigned when a domain user or group  is created
	Used by AD to identify objects internally
# Things To Understand
***
	AD is designed to be backwards compatible so many features are not secure by default
		This is good news for us as the attacker
	Essentially any member connected to the domain can read the whole database regardless of privlage level
		This is good because it leaves us with a wide open path to begin enumerating the environment.
