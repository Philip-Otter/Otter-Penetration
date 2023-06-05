# Back End Server "Stacks"
***
## https://en.wikipedia.org/wiki/Solution_stack
***
	A nice list of different types of stacks.

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
# Resources & General Notes
***
## HTTPS
***
### HTTPS Flow
#### ![[Pasted image 20230604185023.png]]
	From HTB Academy
