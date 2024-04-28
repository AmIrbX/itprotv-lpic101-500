ACL -> Access Control List

## Why use ACL?
the problem with POSIX permissions is that we can't set a permission for a user other than the owner.
for example if we have 3 users:
1. `nik` -> admin
2. `eric`
3. `jack`
and now if `nik` creates a file and wants  `eric` to be able to write to the file but `jack` 
shouldn't be able to write to the file.

in this scenario we can't achieve our goal with POSIX permissions so this is when ACL comes.

## How to use ACL?
### 1. Check whether ACL is enabled for the hard disk
```
	# Print your file system table
	cat /etc/fstab 

	# Output:
	
	# / was on /dev/sda2 during installation
	UUID=UUID /               ext4    errors=remount-ro 0       1
	# /boot was on /dev/sda4 during installation
	UUID=UUID /boot           ext4    defaults        0       2
	# /boot/efi was on /dev/sda5 during installation
	UUID=UUID  /boot/efi       vfat    umask=0077      0       1
	# /home was on /dev/sda6 during installation
	UUID=UUID /home           ext4    defaults        0       2
	# swap was on /dev/sda3 during installation
	UUID=UUID none            swap    sw              0       0
```

```
	sudo tune2fs -l /mount/point

	sudo tune2fs -l /dev/sda5 | grep "acl"
```

- `tune2fs` -> A tool to modify or list information of a hard disk partition
- `-l` -> an argument (list information)



### 2. Use `setfacl` and `getfacl`
#### `setfacl`

```
	setfacl [-m,-s,-x] [g,u,o]:username_or_group:[r,w,x] filename_directory
```
- `[-m,-s,-x]`
	- `-m` -> Modify or add permission
	- `-s` -> Replace
	- `-x` -> Removes a permission
- `[g,u,o]`
	- `g` -> specifying the permission for `group members`
	- `u` -> specifying the permission for `USER/OWNER`
	- `o` -> specifying the permission for `others`
- `[r,w,x]`:
	- `r`  -> READ
	- `w`  -> WRITE
	- `x`  -> EXECUTE


#### `getfacl`

we use `getfacl` to see the ACL permissions.
```
	getfacl filename_or_directory
```



### How to enable inheritance for ACL Based permissions?

```
	setfacl -m d:g:nik:rw filename_or_directory
```

**Only NEW files will inherit the permissions.**
### How to know if ACL is enabled for a folder?
just use `ls -l` and check the permissions's column. if there's a `+` after the last character 
it means that folder is using ACL.
```
	ls -l
		drwxrwxr-x+ 2 ruinedrome ruinedrome 4096 Apr 28 23:54 acl
```


