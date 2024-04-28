## What is pipe?
pipe is a character on the keyboard.
```
Pipe -> |
```
We can use pipes to redirect **commands** output to another **command**. 


### Example:
```
	dmesg # a log file for connected input devices

	# What if we find our harddrive's status? it's a pretty long file so that's hard. BUT
	dmesg | grep sda5	
```

All output from `dmesg` will be redirected to `grep` command.
- It is possible to use piping several times and repeatedly.

## There's a problem
Some programs in Linux doesn't support piping.
for example if we have a text file with folders name and we think we can create them easily with pipes, right?
```
	cat filenames.txt | mkdir
```
  but `mkdir` doesn't support piping and now `xargs` comes to solve it.

```
	cat filenames.txt | xargs mkdir
```

and now another problem... . 
`bash` expects another filename after a space so there may be too many files if we have a folder like `i am dumb`. 
output of a folder name like `i am dumb` will be:
- `i` -> folder
- `am` -> folder
- `dumb` -> folder

### How to escape space in bash?
There are 2 general way. First using `\` before a space or putting the file name in quotes '`file name`'
```
	ls 
		'file name'
		file\ name
```

