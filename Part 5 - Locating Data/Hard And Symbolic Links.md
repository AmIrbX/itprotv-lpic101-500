
Links = Shortcuts

Types of Links
1. Hard Links
2.  Symbolic Links (Soft Links)

## What is the difference between hard and soft links?
### Hard Links
- Points to a file
- can not link or point to a file in another file system 
- Hard Links point to the raw data
- these links work even if the original file is deleted
```
	HD1 -> hard_link
	HD2 -> script.sh
```
we can not create a hard link in `HD1` which is `Hard Disk 1` to `script.sh` in `HD2` or `Hard Disk 2` 

**If i create 3 hard links from `script.sh` and i delete the original file 
the other 3 hard links will still work**

#### How to see number of hard links?

```
	ls -l
		permissions  number_of_hard_links   username   group_name   size  date_of_modification  Folder_or_file
		drwxr-xr-x  2 ruinedrome ruinedrome       4096 Apr 17 19:41 Documents
```

- The 2nd Columns is number of hard links.
### Soft Links
- Points to a file or folder
- more flexible
- Symbolic link gets deleted if the original file is deleted

## How to create links?

### Links to files:
```
	ln dracula.txt hard_link_name.txt # Hard link
	ln -s dracula.txt soft_link.txt # Sodt link
```

### Links to directories:
```
	ln -s /target/directory /destination/link_name
```

- `/target/directory` -> the directory we want to create a link of
- `/destination/link_name` 
	 the folder we want to put the link to
	 `link_name` is the link name


