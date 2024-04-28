## What are Redirects and how to use them?
Writing output of a **command** to a **device** or in a **file**

```
	stdout # Standard Out
	stderr # Standard Errors
```

### How to Write output of a command to a file?:

```
	ls -lh > list.txt
```

### How to Append Data to a file with Redirections?
```
	ls >> file.txt
```

### What if we want the content of a file as an input?
```
	sort < file.txt
```

## Nested Redirections

### Example 1 (listing `dirs` and saving them in a file):
```
	# Writes a file called list.txt
	ls -lh | sort > list.txt
```
what this command does is first it lists current directory items (`ls -lh`) and then sorts them (`sort`) and lastly saves them in a file
called `list.txt`. (`> list.txt`)

```
	# Appends the data to the 'list.txt'
	ls -lh | sort >> list.txt  
```

### Example 2 (finding a file and bypassing errors):

```
	# Finds all .doc files
	# There is a problem and that is there are many directories that you as a normal user 
	# can't access so there will be several 'permission denied' errors so if we have a .doc file 
	# it will be above all of these errors and IT IS VERY HARD TO FIND THEM SERIOUSLY.
	find / -name *.doc 

	# Solution: Redirecting all the errors (2) to /dev/null which is like a blackhole
	find / -name *.doc 2>/dev/null
	
```

`2` in`2>/dev/null` part is for redirecting the errors
`stderr` has 2 values
- `1` for successful processes
- `2` for errors 


## What if we want to read and write output of a command into a file?

We can use `tee`.

```
	find / -name *.doc 2>/dev/null | tee file.txt
```







