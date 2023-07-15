# Tricks
***
## BASH
***
### cat < /dev/tcp/ {ip} {port} >{outFile}
- When /dev/tcp is written to it attempts to make a TCP connection to a given IP and port

## Encryption
***
### PowerShell
#### Invoke-AESEncryption.ps1
##### Importing the module
###### `Import-Module ./Invoke-AESEncryption.ps1`
##### Encrypting
###### `Invoke-AESEncryption -Mode Encrypt -Key "{password}" -Path {filePath}`
### OpenSSL
#### `openssl enc -aes256 -iter 100000 -pbkdf2 -in {inFile} -out {outFile}`
- -pbkdf2
	- Password based key derivation function 2
## Netcat
***
### Destination
#### `nc -l {listenPort} --recv-only > {outFile}`
- --recv-only
	- Closes the connection once the file is transferred 
### Host
#### `nc {IP} {port} < {inFile}`
- Connection should close automatically after the file is transferred 

## PowerShell
***
### Invoke-WebRequest
#### Evading user agent filters
##### `Invoke-WebRequest {URL} -UserAgent [microsoft.powershell.commands.PSUserAgent]::{userAgent} -OutFile {outFile}`
##### Listing user agents
###### `[microsoft.powershell.commands.PSUserAgent].GetProperties()`
### PS Sessions
	Remember enabling PowerShell remoting creates an HTTP and HTTPS listener
		These are on TCP 5985 and 5986
#### Creating a new session
##### `$session = New-PSSession -ComputerName {compName}`
#### Copying Files
##### Local to remote
###### `Copy-Item -Path {filePath} -ToSession {session} -Destination {remoteFilePath}`
##### Remote to local
###### `Copy-Item -Path {remoteFilePath} -Destination {filePath} -FromSession {session}
`
## RDP
***
### Mounting files via RDP
#### rdesktop
##### `rdesktop {ip} -d {domain} -u {user} -p {password} -r {comport:device}={drive}`
- example:  `rdesktop ... ... -r disk:linux='etc/share'`
#### xfreerdp
##### `xfreerdp /v:{IP} /d:{domain} /u:{user} /p:{password} /drive:{drive},{path}`
## SCP
***
### `SCP {localFile} {user}@{IP}:{remoteFileLocation}`
# Troubleshooting
***
## Firewalls
***
### Base 64
	Useful when firewall is preventing downloads 
#### Encoding
##### `base64 {binaryFile} -w 0 > {encodedFile}}`
- -w 0 disables line wrapping

#### Decoding
	Post file transfer
##### `echo {encodedFile} | base64 -d > {outBin}`
## Validation
***
- md5 sum
	- Linux and Windows
- file command
	- Linux