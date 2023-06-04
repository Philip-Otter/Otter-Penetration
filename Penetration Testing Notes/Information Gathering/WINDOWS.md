# Commands To Gather Data
***
## AD Information
***
### Get-ADUser & GetADGroup
##### Useful Flags & Searches
- -Filter
	- ==Syntax:==  Get-{ADUser|ADGroup} -Filter {field} -Like {term}

## Environment Information
***
### set
	Used to set vairable values but can be used without any flags to return all currently assigned variables.
### $env
##### Options
- ==Syntax:==  $env:{option}
- PSModulePath
### Get-ExecutionPolicy
	Checks PowerShell execution policy
##### Useful Flags
- -List
	- Provides us with more than just our current sessions execution policy
- -Scope {scopeValue}
	- Allows us to pick our scope for the command
	- Process
	- CurrentUser
	- LocalMachine
	- UserPolicy
	- MachinePolicy
## Network Information
***
### net
	Running this is pretty noisey.
	Provides a huge wealth of information!
### ipconfig
### Get-NetIPAddress
	Similar to ipconfig

### Get-NetRoute
	Prints out our routing table

### Get-IPInterface
	Gets all visible network adapter properties
### arp
###### Useful Flags
- -a/-g
	- Returns the ARP tables.

### netstat
	Show network connections to our host
##### Useful Flags
- -n
	- Does not resolve IPs to Hostnames

### Test-NetConnection
	Powerful tool for testing and teasing out network data
## Registry Information
***
### Get-Item Property -path {registyPath}
### Reg
### Get-ChildItem -Path {registryPath}
## System Information
***
### whoami
###### Useful Flags
- /all
### systeminfo
### ver
	Returns the Windows build information
hostname
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

## Windows Event Logs
***
### wevtutil
### Get-WinEvent
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





## Find Data
***
### find str
	Finds a string

## Sort Data
***
### sort
	Sorts data given
	0-9 A-z
### ft
	Alias for Format-Table
	Can even select properties with it
##### ==Syntax:==  ft {Properties(seperated by commas)}
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

# File Extensions
***
## .psd1
	PowerShell module manifest file
## .psm1
	PowerShell script module file
	Contains PowerShell code
## .evtx
	Windows Event Log files

# Protocols
***
## Kerberos
***
	Network level authentication protocol
	Common in AD environments
- Port 88
- TCP/UDP
## LDAP
***
	Lightweight Directory Access Protocol
	Used for authentication and authorization with various directory services
- Port 389
- TCP/UDP
## LDAPS
***
	Like LDAP but with a TLS/SSL connection
- Port 636
- TCP/UDP

## RDP
***
	Remote Desktop Protocol
- Port 3389
- TCP

## SMB
***
	Server Message Block
- Port 139
	- Used by SMB that talks over NeTBIOS
	- NetBIOS over TCP (NBT)
		- Also supports UDP
- Port 445
	- Modern SMB post Windows 2000
	- TCP/UDP
		- Windows Vista & Windows Server 2008 with SMB 2.0.2 and up requires TCP

## WinRM
***
	Windows Remote Management
	Microsoft implementation of WS-Management Protocol
	Used to manage hardware and software functionality of hosts
	Can be used for host enumeration and scripting
- WinRM HTTP
	- Windows 7 and on
		- Port 5985
	- Pre-Windows 7
		- Port 80
- WinRM HTTPS
	- Windows 7 and on
		- Port 5986
	- Pre-Windows 7
		- Port 443
# Stealth
***
## Theory
***
### PowerShell
	PowerShell is noisey and keeps detailed logs. If you don't need it's functionality stick with CMD which has less logging.
	PowerShell usage itself can cause alerts to go off depending on security configurations.
#### Execution Policy
	We should be concious of changing our execution policy. If we do change our policy we should change it back to cover our tracks. We can also use the -scope tag with the Set-ExecutionPolicy to limit the change of our execution policy changes to avoid detection.
### CMD
	Users are likely not to be using CMD.
	CMD usage can cause alarms to go off but it is stealthier than PowerShell.

# User Account Types
***
	Four main types
## Service Accounts
***
## Built-In Accounts
***
### Administrator
### Default Account
	Used to run multi-user auth apps
### Guest Account
	Disabled by default
### WDAG
## Local Users
***
## Domain Users
***

# Valuable Data Locations
***
## \\AppData\
***
- Config files
- Temp Saves
## C:\\Users\{user}\
***
- VPN Keys
- SSH Keys
## C:\\Users\\{user}\\AppData\\Roaming\\Microsoft\\Windows\\PowerShell\\PSReadLine\\ConsoleHost_history.txt
***
- Console History
## Get-Content (Get-PSReadlineOption).HistorySavePath
***
- Console History
## Get-Clipboard
***
- Clipboard Contents
## Scheduled Tasks
***
	We could find all sorts of potentially valuable information hidden in the schedualed tasks.

## C:\\Windows\\System32\\winevt\logs
***
- Windows Event Logs
- Event Logs have .evtx extensions