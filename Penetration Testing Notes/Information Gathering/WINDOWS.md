
# Commands To Gather Data
***
## Network Information
***
### net
	Running this is pretty noisey.
	Provides a huge wealth of information!
### ipconfig
### arp
###### Useful Flags
- -a/-g
	- Returns the ARP tables.
## System Information
***
### whoami
###### Useful Flags
- /all
### systeminfo
### ver
	Returns the Windows build information
hostname
## Environment Information
***
### set
	Used to set vairable values but can be used without any flags to return all currently assigned variables.
## Service Information
***
### sc
#### Useful Syntax & Flags
- query
	- ==Syntax:==  sc query {options}
		- type={type} ==Defaults to service==
			- driver
			- service
			- userservice
			- all
		- state={state} ==Defaults to active==
			- active
			- inactive
			- all
- start
	- ==Syntax:==  sc start {service name}
- stop
	- ==Syntax:==  sc stop {service name}
- config
	- ==Syntax== sc config {service name} {property}={updatedValue}


# Commands To Compare & Sort Data
***
## Compare Files
***
### comp
	Only tells you that the files dont match.
#### Useful Flags
- /N=number
	- Compares Only The First Specified Number Of Lines
### fc
	Compares the two files and displays the differences.





## Sort Data
***
### sort
	Sorts data given
	0-9 A-z
## Find Data
***
### find str
	Finds a string