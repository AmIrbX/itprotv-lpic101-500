
### What is Execution Priorities?
it is for monitoring and controlling how much resources each application can use by prioritizing them.


### How To change Execution Priorities?
#### tool: Nice
```
	sudo nice priority_num cmd
	# e.g:
	sudo nice -12 sha256sum /dev/sda5
```

**Default settings -> all programs have the same priority**

**Range of the `priority_num`  : -20 ~ 19  -> lower number means higher priority**

### How to see other programs execution priority?
```
	top  # There is a column 'NI' for execution priority
```


### How to change execution priority while the program is running?

```
	sudo renice new_priority_num process_id -u username
```

`renice` is the tool we use to change the priority number while the program is running and `-u username`  is for when there are two processes and we want to terminate only one user's program.


### Ways to kill a program
```
	kill -l
```

**Important Signals:**
1. SIGHUP -> Signal Hang Up -> reloads a program(most of the times it won't work)
2. SIGKILL -> Terminates a job or program
3. SIGTERM -> asks the program to terminate itself


#### Kill all instances of a program 
```
	killall process_name
	# e.g
	killall chrome
```

- Useful when you can't or you don't know the process id




