---
tags: Keys,Linux_File_Permissions, SSH, Linux
---
# Tricks
***
## Using A Key File
***
- -i {keyFile}
# Troubleshooting
***
## Permissions
***
	SSH keys require stricter permissions for them to work.
- Possible fix
	- ==Syntax:==  chmod 600 {keyFile}