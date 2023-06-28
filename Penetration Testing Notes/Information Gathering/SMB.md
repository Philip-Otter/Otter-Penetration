# Hostname Enumeration
***
## nmblookup
***
- ==Syntax:==  nmblookup -A {ip}
## nbtscan
***
- ==Syntax:== nbtscan {ip}

## nmap script
***
- ==Syntax:==  nmap {ip} --script nbstat.nse 

## smbclient
***
- ==Syntax:==  smbclient -L {ip}

# Mounting (Linux)
***
## Tutorial
***
### https://medium.com/@klockw3rk/mounting-vhd-file-on-kali-linux-through-remote-share-f2f9542c1f25
# rpcclient
***
## Usages
***
- ==Syntax:==  rpcclient -U "" {targetIP}
## Commands
***
- srvinfo
	- Server information
- enumdomains
	- Enumerate all domains that are deployed in the network
- querydominfo
	- Provides domain server and user information of deployed domains
- netshareenumall
	- Enumerates all available shares
- netsharegetinfo
	- ==Syntax:==  netsharegetinfo {share}
	- Get information about the selected share
- enumdomusers
	- enumerates all domain users
- queryuser
	- ==Syntax:==  queryuser {RID}
# smbmap
***
## Useful commands
***
- ==Command:==  smbmap -H {targetIp}
	- Should provide us a map of the target's SMB shares

# smbclient
***
- ==Syntax:==  smbclient //{ip}/{share}
## Useful Flags
***
- -n
	- Null session
		- Anonymous SMB access 
- -L
	- Lists the server's shares.

## Executing Local Commands
***
- ==Syntax:==  !{command}
	- Doesn't interrupt the connection

# smbstatus
***
	Command that can provide us with SMB information
		Ran on the machine that is hosting the SMB service 