# Quick Lists
***
## Numbers
***
`for i in $(seq {initialValue} {endValue}); do echo $i >> {outFile}; done`
# Hashing
***
## md5
***
`echo -n {phraseToHash} | md5sum`
	-n
		Disables appending a new line