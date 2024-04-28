## What is `cut`?
It can select a specific part of a text by using a delimiter and column number to cut their values.


----
## How `sort` works?
It starts comparing characters from start of the line to the end of the line. There is a problem with it that we can't tell it to sort files and folders
by name of them in certain commands like `ls -lh`. So we should use a utility to sanitize the input. it is `tr`

---- 
### `tr` command
`tr` is a command for changing a single character or a sequence of characters or deleting a character to another.

```
	ls -lh | tr -s " " "	"
```
**How to type tab?**
```
	Ctrl + V
	Press Tab
```


`tr -s " " ","` :
- `-s` -> sequential characters. for example:
	`i    am            dumb` 
- `" " "	"` replaces multiple spaces with a tab
	`i    am            dumb` -> `i	am	dumb`

----

### Advanced usage of `sort`
so now you think we can use `sort` to reverse sort directories by alphabetic order? 
Nah. we still have the problem that sort compares character by character. Solution?
	
```
	ls -lh | tr -s " " "	" | sort -r -t "	" -k 9
```

`sort -r -t "	" -k 9` :
- `-r` -> reverse sorting
- `-t "	"` -> Specifying the delimiter 
- `-k 9` -> column number to sort by
	- if we consider each `	` or tab character a line between each value 
	    then it's kind of a table so we can use column's number to sort them out

### `cut` command
`cut` command needs to arguments.
- `-d` -> specifying the delimiter 
- `-f` -> column number
	-  we can use multiple numbers to cut multiple columns

```
	ls -lh | tr -s " " "	" | sort -r -t "	" -k 9 | cut -d "	" -f 5,9
	# Output:
	size	name
```





