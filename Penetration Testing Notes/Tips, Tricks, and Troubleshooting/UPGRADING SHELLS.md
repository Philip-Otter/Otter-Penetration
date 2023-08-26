---
tags: Linux, BASH, Python, Python_3, Shells
---
# AWK
***
## `awk 'BEGIN {system("/bin/bash")}'`
# Bash
***
## `SHELL=/bin/bash script -q /dev/null`
### `/bin/bash -i`
# Find
***
## `find . -exec /bin/bash \;-quit`
# Lua
***
## `os.execute('/bin/bash')`
	Run from a script
# Python 3
***
## `python3 -C 'import pty; pty.spawn("/bin/bash")'`
# Perl
***
## `perl -e 'exec "/bin/bash"'`
# Ruby
***
## `exec "/bin/bash"`
	Run from a ruby script
# Vim
***
## `vim -c ':!/bin/bash'`
## Vim escape
- vim
	- :set shell=/bin/bash
	- :shell