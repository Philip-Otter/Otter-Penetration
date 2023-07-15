---
Tags: DNS, Linux, Networking, BIND, Keys, BASH, Automated_Tools, Brute_Forcing, Nmap, Cloud
---
# Footprinting
***
## Nmap
***
### Use "-sC" while scanning the DNS server
## ns query
***
### `dig ns {target} @ {DNSServer}`
- @ is important to us because each DNS server can be configured differently

## Subdomain Brute Forcing
***
### BASH
***
#### `for sub in $(cat {subdomainList}); do dig $sub.{domain} @ {DNSServer} | grep -v 'j\|SOA' | sed -r '/^\s*$/d' | grep $sub | tee -a subdomains.txt; done`
### DNSenum
***
#### `dnsenum --dnsserver {DNSIP} --enum -p 0 -s 0 -o subdomains.txt -f {subList} {domain}`
## View All Available Records
***
### `dig any {target} @ {DNSServer}`
## Version Query
***
### `dig CH TXT version.bind {targetIP}`
- Only works if the entry actually exists

# Information Gathering Sites
***
## Grayhat Warfare
***
	We can use this to find public bucket information
### https://buckets.grayhatwarfare.com/
## DNS Dumpster
***
#### https://www.nmmapper.com/
##### Documentation
***
###### https://dnsdumpster.readthedocs.io/en/latest/
##### Source Code
***
###### https://github.com/wangoloj/dnsdumpster
# Local Configuration
***
## name.conf.local
***
	Located at `/etc/bind/`
### Zones
***
	name.conf.local can define different zones
		each zone gets it's own file
			Zone files are text files that describe the DNS zone with the BIND format
				The BIND format is the industry preferred
			Points at delegation in the DNS tree
			Describes the zone completely
			Contains precisely one SOA record
				This is usually at the start of the file
			Contains at least one NS record

# Records
***

| Record | Information |
|---------|---------------|
| A | Subdomain information|
| MX | Mail server information |
| NS | Name server information |
|TXT | Text records. These can often contain verification keys for third-party providers, SPF, DMARC, and DKIM information |

# Zone Transfer
***
	The transfer of zones to another DNS Server
	Generally happens over TCP port 53
	Called Asynchronous Full Transfer Zone
		AXFR for short
	Zones are kept synced to prevent failures resulting in downtime
		Happens at a set interval
			Usually 1 hour
		Compares serial numbers of SOA records of master and slave servers
	A secret key is used for this transfer
		rndc-key
	The original data is located on the primary name server
		DNS entries are generally only created, modified, or deleted on the primary server
		The primary is a master server while secondaries can be either master or slave servers
## Zone Transfer Query
***
	If the 'allow-transfer' option was configured using a subnet or set 'any' other zones could potentially be queried.
		Even internal zones that would show internal IPs and Hostnames
### `dig axfr {target} @ {DNSServer}`
