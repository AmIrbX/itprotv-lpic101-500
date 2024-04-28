

### Search

Vim is case sensitive.

#### Inside of the file:
```
/mina  # Searches for "mina" - Only One instance
```
#### Outside of the file:
```
	vim +/mina story.txt # Goes to the first line that has "mina"
```

#### Repeatedly Search:
```
	/ # Search for the last word again - Just hit "Enter"
```


### Replace
```
	:s/mina/ramin # Replaces "mina" with "ramin" - Only one line
```
####  Multiple Line Replacement:
```
	:1,1000s/mina/ramin # Searches from lines 1 to 1000 and finds all "mina" instances and replaces them with "ramin"
```



### How to undo our file?
```
	# 1st Method:
	:q! # You can override your changes 

	# 2nd Method:
	:e! # Reloads the file from hard-disk 

```

**These two works the same**



