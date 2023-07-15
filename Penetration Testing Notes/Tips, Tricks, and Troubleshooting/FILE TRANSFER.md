# Tricks
***
## BASH
***
### cat < /dev/tcp/ {ip} {port} >{outFile}
- When /dev/tcp is written to it attempts to make a TCP connection to a given IP and port
## Netcat
***
### Destination
#### `nc -l {listenPort} --recv-only > {outFile}`
- --recv-only
	- Closes the connection once the file is transferred 
### Host
#### `nc {IP} {port} < {inFile}`
- Connection should close automatically after the file is transferred 
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