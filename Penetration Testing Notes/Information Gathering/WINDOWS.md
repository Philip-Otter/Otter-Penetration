
# Stealth
***
## Theory
***
#### PowerShell
	PowerShell is noisey and keeps detailed logs. If you don't need it's functionality stick with CMD which has less logging.
	PowerShell usage itself can cause alerts to go off depending on security configurations.
#### CMD
	Users are likely not to be using CMD.
	CMD usage can cause alarms to go off but it is stealthier than PowerShell.
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
	sc query will provide you with what the permissions the current user has on each individual service
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
### tasklist /svc
### wmic service list brief
	Lists services using Windows Manegment Instrumentation Command
	!!!!! WMIC is depreciated !!!!!

## Scheduled Task Information
***
### schtasks
#### Useful Flags
- /Query
	- List all scheduled tasks
- /S
	- Specify a remote system
-  ==Syntax:==  schtasks {comandFlag} /TN {taskName}
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

# Commands To Find Commands
***
## PowerShell
***
### Get-Command
	Lists all available commmands
##### Useful Flags
- -verb
	- ==Syntax:==  Get-Command -verb {verb}
### Alias
	List all set aliases
	By default there are a lot of linux like aliases in place
### Get PowerShell Keyboard Shortcuts
***
	CTRL+ALT+SHIFT+?
### Finding Options & Functions For A cmdlet
***
### Get-Help
	Similar to linux man page
##### Useful Flags
- -Online
	- Pulls the online man page for the command in a web browser
### Get-Member
	Gets the properties and methods of objects
### Get-Module
	Finds PowerShell Modules
	By default it only grabs the modules that are loaded into our current session
##### Useful Flags
- -ListAvailable
	- Shows Installed but perhaps not loaded modules
