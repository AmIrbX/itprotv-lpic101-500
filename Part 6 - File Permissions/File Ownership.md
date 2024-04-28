## How to view file's permissions?
```
	ls -l
	# Output:
	permissions  number_of_hard_links   username   group_name   size  date_of_modification  Folder_or_file_name
	
	# Example:
	
	drwxr-xr-x  2 ruinedrome ruinedrome 4096 Apr 17 19:41 Documents  
```

**With creating a username in the Linux, a group with the same name will be created.**

## How to change ownership of a file?

```
	sudo chown new_owner filename

	sudo chown bob dracula.txt
```

- `chown` -> a tool we use to change file's ownership
- `bob` -> an **existing** username 
- `dracula.txt` -> the file we are modifying

## How to change ownership of all files in the current directory?

```
	sudo chown -R new_owner /folder/path

	sudo chown -R nik /home/nik/Documents
```

- `-R` -> an argument (Recursive)
- `nik` -> a username
- `/home/nik/Documents` -> the directory 


## How to change group's ownership with `chown`?

```
	sudo chown new_user_name:new_group_name filename

	sudo chown nik:nik dracula.txt
```

- `nik:root` -> `nik` is a user and `root` is a group

### How to change only the group?

Just leave the new user name field blank.
```
	sudo chown :nik dracula.txt
```




### Is there an alternative way to change group's ownershuip?

```
	sudo chgrp new_group_name filename
	sudo chgrp new_group_name *
	sudo chgrp new_group_name -R /Folder/Path
```

- `chgrp` -> the tool to **only** change the group
- `*` -> a sign that indicates of all files and folders in the current directory
- `-R /Folder/Path` -> an argument (Recursive change)



## How to make the items inside a folder inherit their parents's permissions?

With `stickty bit` you can enable inheritance for items inside a folder. 
### How to know if `sticky bit` is added to folder?
```
	ls -l
	drwxr-xr-x  2 ruinedrome ruinedrome 4096 Apr 17 19:41 Documents 
```

let's explain the permissions here:
- `d` -> indicates a directory
- `r` -> READ permission
- `w` -> WRITE permission
- `x` -> EXECUTE permission
- `-` -> Permission not allowed
If we split the permissions string into 3 parts, it will come out this way:

| Directory? | USER/OWNER | Group | Others |
| ---------- | ---------- | ----- | ------ |
| d          | r w x      | r-x   | r-x    |
- As a USER/OWNER you have READ(`r`),WRITE(`w`),EXECUTE(`x`)
- All group's members (except the owner) have READ(`r`) and EXECUTE(`x`) but they can't WRITE (`-`)
- Others that aren't members of that group have READ(`r`) and EXECUTE(`x`) but they can't WRITE (`-`)

---
### So where is `sticky bit`?
if instead of `x` or EXECUTE permission, `s` character is there, that means
all objects inside that path inherit their permissions from this folder.
```
	drwsr-sr-x  2 ruinedrome ruinedrome 4096 Apr 17 19:41 Documents 
```

### How to create `sticky bit` 

```
	sudo chmod g+s,u+s /Folder/Path
```

- `g+s` -> add `sticky bit` to groups's permissions
- `u+s` -> add `sticky bit` to user's permissions
#### Note :
1. `sticky bit` only applies to new objects created in the folder.
2. when you move (`cut`) a file to a different place, `sticky bit` will be removed
	and won't inherit the parent's permissions anymore. (==Copying== works) 





