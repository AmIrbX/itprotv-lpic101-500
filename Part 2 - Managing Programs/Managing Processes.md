
### View Processes 

```
	ps aux # All processes
	ps a # Current shell processes
```

### Find Processes

```
	pgrep process_name # Searches by process name output: PID
	
	pgrep -u user process_name # Searches by process name and shows only process                                  related to the specified user

	ps aux | grep bash # First lists all of the processes and then with grep 
	                     command, it will only show bash proesses
```
### Monitoring Processes

```
	top # Shows processes that use more resources 
		-> Shift + M # Sorted By Memory Usage
		-> Shift + P # Sorted By CPU Usage
```


### Kill Processes 
```
	kill PID
	top -> type "k" then type the pid
```


### Background & Foreground Processes 

```
	Ctrl + Z # puts the running program in Background - Output: job_id
	bg # shows background processes
	fg job_id # Resumes the background program
```

### Scenario:
If we put an application in background and then close the shell session what will happen to the background programs?
All of them will be gone.
#### Solution: Using Services
```
	systemctl -> managing services
	journalctl -> Viewing Service's logs
```


