# Back End Server "Stacks"
***
## https://en.wikipedia.org/wiki/Solution_stack
***
	A nice list of different types of stacks.

# DNS
***
## Encryption
***
	Mainly unencrypted
### DNS over TLS (DoT)
### DNS over HTTPS (DoH)
### NSCrypt
	Encrypts traffic between the computer and the name server
## Types of DNS Servers
***
- DNS Root Server
	- Responsible for tor TLDs (Top Level Domains)
	- Only requested if the name server does not respond
	- Links domain and IP address 
	- ICANN coordinates the work of the root name servers
		- 13 around the globe
- Authoritative Namesever
	- Holds authority for a particular zone
	- Only answers queries from their area of responsibility 
	- Their information is binding
	- If a question cant be answered by this server it goes on to the root server
- Non-Authoritative Nameserver
	- collects information on a specific DNS zone
		- Done through iterative DNS querying
- Caching DNS Server
	- Cache information from other name servers for a specific period of time.
		- This period of time is determined by the authoritative Nameserver
- Forwarding Server
	- Forwards DNS queries to another DNS server
- Resolver
	- Perform name resolution locally in the computer or router
# Fuzzing
***
## ffuf
***
### Useful flags
- -u
	- URL
- -w 
	- Word list
- -t
	- Sets the number of threads
- -fc
	- filter code
- -mc
	- match code
- -c
	- colorize
- -ic
	- Remove copyright comments from word list
- -recursion
	- Set recursive fuzzing
- -recursion-depth
	- Set the recursion depth
- -e
	- Specify extension(s)
		- With the period!
- -fs
	- filter size
- -d 
	- Set the data field
- -X
	- Select http method
- -mr
	- Match regular expression
### Assigning keywords
- ==Syntax:==  ffuf -w {wordlist}:{keyword} -u {url}
	- To be able to use recursion the url has to end with the FUZZ keyword
## Vhost Fuzzing
***
### Vhosts vs subdomains
- Vhosts
	- Served on the same server
	- Has the same ip address as the main domain
- subdomains
	- Ip address differs from the main domain
# Headers
***
## Security Headers
***
### Content-Security-Policy
	Dictates teh websites policy torwards externally injected resources
### Strict-Transport-Security
	Prevents HTTP traffic
### Referrer-Policy
	Dictates whether the browser should include the value specified via the referer.
	Can help avoid leaking URLs and information

## Methods
***
### GET
### POST
### HEAD
	Returns the headers that would have been returned if a GET request was made.
### PUT
	Create new resources on the server
### DELETE
### OPTIONS
	Returns information about the server
### PATCH
	Applies partial modifications to resources
### CONNECT
	Reserved for use with proxies, firewalls, and other security devices.
	Allows for tunneling over HTTP
		SSL tunnels
# Responses
***
## ==200==
### OK
## ==201==
### Created
	Success status
	Indicates that the request has led to the creation of a resource
## ==301==
### Moved Permanently
## ==302==
### Found
## ==400==
### Bad Request
## ==401==
### Unauthorized
## ==403==
### Forbidden
	Client doesnt have the access rights to this content
## ==404==
### NOT FOUND

## ==405==
### Method Not Allowed
	The Server knows what this request is but it has been disabled
## ==408==
### Request Timeout
## ==500==
### Internal Server Error
	Server has ran into a situation that it doesn't know how to deal with it
## ==502== 
### Bad Gateway
## ==504==
### Gateway Timeout
# Requests
***
## curl
***
### Useful Flags
- -I
	- Provides Header Values
- -O
	- Output to file using remote file name
- -o
	- Output to file with ==defined== file name
- -k
	- Skip Certificate check
- -H
	- Set header values
- -u 
	- Provide credentials to the site
	- ==Syntax:==  curl -u {user}:{password} {URI}
- -d, --data
	- HTTP data
- -X
	- Set Request type
	- ==Syntax:==  curl -X {requestType} {URI}
### Pipe into jq to format
- ==Syntax:== curl -s ... | jq
# Resources & General Notes
***
## HTTPS
***
### HTTPS Flow
#### ![[Pasted image 20230604185023.png]]
	From HTB Academy

