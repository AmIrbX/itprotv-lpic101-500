We will use `rgrep` to find files.

## How `rgrep` works?
`rgrep` searches a string in a file or files.
So if we can't remember the name of the file we may know the content
of the file to search for it.

```
	rgrep "dracula" ~/
	grep -r "dracula" ~/
```
`rgrep`**or**`grep -r`**is ==case-sensitive==**

## How to make `rgrep` case-insensitive?
#### Using regex
```
	rgrep "[d,D]racula" ~/
```

#### Using an argument
```
	grep -ri "Dracula" ~/
	rgrep -i "Dracula" ~/
```

- `-ri`-> `i` case-Insensitive search

## How to limit the output to only file names?
```
	grep -ril "Dracula" /
	rgrep -il "Dracula" /
```

- `-ril` -> `l` lists only file names



## How to search for files that doesn't have a string?

```
	rgrep -vi "fuck" ./
```

- `-vi` -> `v` for`invert match` 





