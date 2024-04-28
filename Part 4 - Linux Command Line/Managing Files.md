
### Show Files and Directories

```
	ls # Shows current directory's file and folders
	ls -l # shows extra info like size,last date and time of changed,permissions
	ls -h # Makes the size values human readable
	ls -a # Shows hidden files and directories besides other items
```


### Read Files Content
```
	# An usual way of viewing contents on the screen. it's not recommended for long files.
	cat file.txt 

	# Allows for scrolling down and makes it better to read file's content. The downside is that it doesn't allow you 
	# to scroll up and read passed text
	more file.txt

	# It has both functionality to scroll up and down and less has a vim-like environment so we can search and replace 
	# strings which is great! (Recommended)
	less file.txt
	
```


#### How to read only a part of a text file?
```
	head file.txt # First 10 lines
	tail file.txt # Last 10 lines

	# First 20 Lines
	head -n 20 file.txt 
	# Last 20 Lines
	tail -n 20 file.txt
```

#### How to read a file like log file while a change might happen to it?

```
	tail -f file.txt
```

### Moving and renaming files
```
	# 'mv' can do 2 things. 1st is renaming a file or folder. 2nd is to cut and paste.

	# Moving the item to another path
	mv file_or_folder /target_path

	# Reaming an item
	mv file_or_folder new_name

	# Doing renaming and moving it
	mv log3.txt ~/Desktop/log.txt

```

### Create and remove a folder
```
	# Creates a folder
	mkdir folder_name

	# Removes a folder 
	rm folder_name

	# Remove a folder and all of its content
	rm -rf /directory
```





