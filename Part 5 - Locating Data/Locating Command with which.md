### How to Know what is the type of the command we are using?
```
	type ls
	# Output -> ls is aliased to `ls --color=auto'
	# `ls` is an alias
	
	type cat
	# Output -> cat is hashed (/usr/bin/cat)
	# `cat` is a binary file located in `/usr/bin/`
	
```


## How to locate the binary file of a cmd?
### 1st Way -> Using `locate`
```
	locate uname
```


|   Pros   |                 Cons                  |
| :------: | :-----------------------------------: |
|   Fast   |     Not available in all distros      |
| Powerful |         needs maintenance **          |
|          | will not tell me which file i'm using |
** `locate` use a db to store and search through the hard drive so when you create a new file you should update that database to 
	make sure it works.
		`sudo updatedb`


## 2nd Way -> Using `whereis`
`whereis` only searches through `$PATH` directories and then if it finds the binary file 
`whereis` starts to search for its config and source code files.

```
	whereis cmd
	whereis cat

	whereis -b cat # Only binary files of `cat`
	whereis -s cat # Only source code files of `cat`
```

|       Pros       |                 Cons                  |
| :--------------: | :-----------------------------------: |
| Finds everything |     Only searches through `$PATH`     |
|                  | Will not tell me which file i'm using |

### 3rd Way -> Using `which`
`which` searches through `$PATH`and shows the first match and that first match is the binary file i'm using.

```
	which uname # Only one instance
	which -a uname # All of `uname` instances
```

`which` is the most common tool to find command's binaries as it can find not only the current executable
	file i'm using but also other instances and versions.
