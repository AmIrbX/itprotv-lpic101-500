`find` does not follow `unix` syntax.

```
	find / -name filename.txt
```
- `/` -> the directory we want to search in
- `-name` -> an argument (Search By name)
- `filename.txt` -> the file we want to search

`find` **is ==case-sensitive==**

## How to use `find` to search by size?

```
	find / -name dracula.txt -size 20c
```
 
- `/` -> the directory we want to search in
- `-name` -> an argument (Search By name)
- `dracula.txt` -> the file we want to search
- `-size` -> an argument (Search By Size)
- `20c` -> 20 Bytes

`-size` values are:
- `c` -> Byte
- `k` -> Kilobytes
- `M` -> Megabytes
- `G` -> Gigabytes

```
	find / -name dracula.txt -size -1M
	
```

This command will search through `/` or `root` directory for a file or files with the name `dracula.txt` and size less than `1 Megabytes`.

You can use `-` or `+` to set a size range to search.
```
	find / -name file -size +2M
```


## How to use `find` to search by permissions?

### How to determine who is the owner of a folder?
```
	ls -l
		permissions  number_of_hard_links   username   group_name   size  date_of_modification  Folder_or_file
		drwxr-xr-x  2 ruinedrome ruinedrome       4096 Apr 17 19:41 Documents
```

----

### 1st Way to search by permissions
```
	find ~ -perm /g=r,u=w
```
- `-perm` -> an argument (Search By permissions)
- `/g=r`-> all files or directories that have group(`g`)'s read (`r`) permission.
- `u=w`-> files and directories that have user(`u`)'s write(`w`) permission.

### 2nd way to search by permissions
```
	find /shared -user username
	find /shared -group group_name
```

- `-user` -> an argument (Search By owner of the files)
- `-group` -> an argument (Search by group)


### 3rd way to search by permissions

```
	find / -uid 1000 
	find / -gid 1000
```

- `-uid` -> an argument (Search By User ID)
- `-gid` -> an argument (Search By Group ID)

#### How to know our user id and group id?
```
	id
```








## How to limit the depth of search with `find`
depth of search is how many sub-directories we want `find` to search in.
for example if we have a file called `General_science.pdf` in the `/home/dpezet/Documents` and `/Documents` has 2 sub-directories 
`/Books` and `/Study_Material`  and we want only `.pdf` files in the `/Documents` not the sub-directories.

Tree List:
```
	/Documents
		General_Linux.pdf
		/Books
			General_science.pdf
		/Study_material
			Linux_in_action.pdf
```

Command:
```
	find ~/Documents/ -name *.pdf -maxdepth 1
```
- `*.pdf` -> all pdf files
- `-maxdepth 1` -> search only the current directory and DO NOT go into sub-directories.


