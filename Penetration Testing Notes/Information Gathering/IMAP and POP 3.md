---
tags: IMAP, POP_3, Email, cURL, Encryption, Nmap, Automated_Tools
---
# Commands
***
## IMAP
***
- LOGIN
- LIST
	- `LIST "" *`
		- Lists all directories
- CREATE
	- Creates a mailbox
- DELETE
	- Deletes a mailbox
- RENAME
	- Renames a mailbox
- SELECT
	- Selects a mailbox
- UNSELECT
- FETCH
	- `FETCH {ID} all`
		- Retrieves data associated with a message
- CLOSE
	- Removes all messages with the "deleted" flag
- LOGOUT
## Command Tags
***
	Command tags are a just a user generated value that proceeds the command.
	The point of command tags is so that we can track what the server responses are for each command that we run.

## POP 3
***
- USER
- PASS
- STAT
	- Request the number of saved emails in the server
- LIST
	- Request the number and the size of all emails
- RETR {ID}
	- Requests the server deliver the email
- DELE {ID}
	- Requests the server deletes the email.
- CAPA
	- Display server capabilities
- RSET 
	- Requests the server to reset the transmitted information
- QUIT

# Footprinting
***
## cURL
***
#### `curl -k {target} --user {username}:{pass} -v`

## Nmap
***
### use "-sC" flag
## OpenSSL
***
### `openssl s_client -connect {taret}:{pop3/imaps}`
# How It Works
***
	Runs on ports 110, 143, 993, 995
		Ports 993 and 995 use TLS/SSL