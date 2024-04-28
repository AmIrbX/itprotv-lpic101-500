### Bash Settings
- Profiles -> Designed For working with Multiple shells
- `bashrc` -> Only for Bash

#### `bashrc` settings
It applies the settings only to one user.

```
ls -a /home/$USER
	/~/.bash_history -> It saves all cmds used after boot (Source file of `history' Command)
	/~/.bash_logout -> Commands the bash runs after we logout from bash
	/~/.bashrc -> Bash Settings
```

`bashrc` settings have ==2== Scopes:
- User specified -> `/home/$USER/.bashrc`
- Global Settings -> for all users. Locations:
	- `/etc/bash.bashrc`
	- `/etc/profile.d`

 **It is recommended to not change global configs**
#### Aliases
We can use aliases to save time using long commands.
```
	ls -> ls --color=auto # ls is an alias
```

we can see aliases with  `alias` command.


##### How to add an alias?
 We should add our custom `alias` in `.bashrc` file.
```
	nano ~/.bashrc
		# add this line
		alias sudov='sudo --version'

	sudov -> Version of sudo command.
```

#### How to add a global variable in our `bashrc`?
- Single Variable -> only one variable 

```
	nano ~/.bashrc
		NN="laptop'
		export NN
```

- Multi Variables

```
	nano ~/.bashrc
		set - allexport
```
#### How to declare a function in bash?


```
	vim ~/.bashrc
		function_name()
		{
			commands
		}
```


---
#### A Recommended Tip
`bash` by default can't run scripts on current directory. we can solve this problem by adding `.` meaning **Current Directory** to the $PATH.

```
USER:~$ ls 
		script.sh

USER:~$ script.sh
	'script.sh' is Not found
	
USER:~$ ./script.sh
	Hello World!
```

Solve:
```
	nano ~/.profile
		# Add This Line At The End Of The File
			PATH=".:$PATH"
```


