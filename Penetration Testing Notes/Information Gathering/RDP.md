---
Tags: Windows, Nmap, Automated_Tools, RDP, Hashing
---
# Footprinting
***
## Nmap
***
### `nmap -sV -sC {target} -p 3389 --script rdp*`
- --packet-trace can be added to inspect the packets contents manually
- the RDP cookie mstshash=nmap can be used to identify our scan and lock us out in a hardened environment.
## rdp-sec-check.pl
***
### `./rdp-sec-check.pl {target}`
### Github
***
#### https://github.com/CiscoCXSecurity/rdp-sec-check