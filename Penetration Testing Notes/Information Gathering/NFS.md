	Network File System
	Used between Linux and Unix systems
	Based on the Open Network Computing Remote Procedure Call protocol
		Exposed on UDP and TCP ports 111
		Uses External Data Representation
	Has no mechanism for authentication or authorization.
		Shifted to the RPC protocol's options
# Configuration
***
## Config File Location
***
- etc/exports 
	- Contains a table of physical filesystems on an NFS server accessible by the clients
		- NFS Exports Table
	- Options
		- rw
			- Read and write permissions
		- ro
			- Read only permissions
		- sync
			- Synchronous data transfer
		- async
			- asynchronous data transfer
		- secure
			- ports above 1024 will not be used
		- insecure
			- ports above 1024 will be used
		- no_subtree_check
			- Disables the checking of subdirectory trees
		- root_squash
			- Assigns all permissions to files of root UID/GID 0 to the UID/GID of anonymous
				- Prevents root from accessing files on an NFS mount
		- nohide
			- if another file system was mounted below an exported directory this directory is exported by its own exports entry
		- no_root_squash
			- All files created by root are kept with the UID/GID 0

# Finding NFS Shares
***
- showmount -e {targetIP}
# Footprinting
***
## Ports
***
	111 and 2049
## nmap
***
- ==Syntax:==  nmap -sV --script nfs* {targetIP}

# Mounting Shares
***
```
mkdir {NFSMountDirectory}
sudo mount -t nfs {targetIP} ./{NFSMountDirectory}/ -o nolock
```
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

