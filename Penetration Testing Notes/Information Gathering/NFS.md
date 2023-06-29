	Network File System
	Used between Linux and Unix systems
	Based on the Open Network Computing Remote Procedure Call protocol
		Exposed on UDP and TCP ports 111
		Uses External Data Representation
	Has no mechanism for authentication or authorization.
		Shifted to the RPC protocol's options
# Versions
***
- NFSv2
	- supported by many systems
	- Originally operated only over UDP
- NFSv3
	- More features than v2
		- Variable file size
		- Better error reporting
	- Not fully compatible with NFSv2 clients
- NFSv4
	- Includes Kerberos
	- Works through firewalls
	- Works on the internet
	- Does not require portmappers
	- Supports ACLs
	- Applies state based operations
	- Version 4.1
		- Only requires a single port to run.