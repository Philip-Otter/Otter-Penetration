# Identifying Hashes
***
## Lengths
***
	Hash lengths can be used to determine the type of hashing algorithm used
- 32 chars
	- NTLM
	- MD5
## Formats
***
	Some hashes follow a set format
- `$id$salt$hash`
	- Delineated with $
	- hash ids
		- 1$ -> md5
		- 2a$ -> Blowfish
		- 2y$ -> Blowfish
		- 5$ -> SHA256
		- 6$ -> SHA512
- hash:salt
## Hashid
***
	Python tool that can detect various types of hashes
### Useful flags
- Can provide appropriate hashcat mode if known
## Hashcat
***
### Example hashes
#### https://hashcat.net/wiki/doku.php?id=example_hashes