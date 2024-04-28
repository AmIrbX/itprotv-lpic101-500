## What is POSIX permissions?
```
	ls -l
	# Output:
	permissions  number_of_hard_links   username   group_name   size  date_of_modification  Folder_or_file_name
	
	# Example:
	
	drwxr-xr-x  2 ruinedrome ruinedrome 4096 Apr 17 19:41 Documents  
```

in UNIX permissions are set with numbers. for example if you wanted to set a READ+WRITE+EXECUTE
for owners of a file and READ + EXECUTE for the group members you have to calculate it this way:
- READ = 4
- WRITE = 3 
- EXECUTE = 1
so it will be a 2 digit number: `75`
**We can at most have a 4 digit number like `1731`**
1. 1st digit is for `sticky bit` 
2. 2nd digit is for `USER/OWNER` 
3. 3rd digit is for `groups`
4. 4th digit is for `others`

but in POSIX we have these permissions as characters so we don't
need to calculate them.
1. `r` -> READ
2. `w`-> WRITE
3. `x`-> EXECUTE
4. `s`-> `sticky bit`

## Using `chmod` to modify,delete and add a permission

```
	sudo chmod [g,u,o] [+,-,=] filename

	sudo chmod u+w,g-x dracula.sh
	# What this command means:
	#    add write permission to user or owner 
	#    remove execute permission of group members
```

- `[g,u,o]`
	- `g` -> specifying the permission for `group members`
	- `u` -> specifying the permission for `USER/OWNER`
	- `o` -> specifying the permission for `others`
- `[+,-,=]`
	- `+` -> Adds a permission
	- `-` -> Removes a permission
	- `=`-> Over-Writes all permissions


### Over-Writing all permissions

```
	sudo chmod guo=rwx dracula.txt
```

- `USER/OWNER` and `Group` and `Others` have all permissions








