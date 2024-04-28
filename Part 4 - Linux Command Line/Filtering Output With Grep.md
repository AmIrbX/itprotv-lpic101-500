`grep` is a search engine.
`grep` stands for -> **G**lobally Search a **R**egular **E**xpression and **P**rint
`grep` is ==case sensitive==.
`grep` has 3 general modes:
- Fixed String -> for a particular word
- Regular Expression
- Recursive search


# How To Use `grep`?

## Fixed String
```
	ls -lh | grep "fire"
	grep -F
	fgrep
```

## Regular Expression
```
	ls -lh | egrep "something"
	ls -lh | grep -E "something"
```

## Recursive Grep
```
	rgrep
	grep -r
```


## Examples:

```
	egrep "Halloween|Christmas" 
	# Shows only strings contain "Halloween" or "Christmas"

	egrep "sda[1,4,6]" 
	# Shows strings -> sda1 , sda4 , sda6

	egrep "^1[0-2]" 
	# "^1" -> strings starting with '1'
	# "[0-2]" -> numbers from 0 to 2 --> 0,1,2

	egrep "sda[0-9]| sda\]"
	# "sda[0-9]" -> sda1,sda2,sda3,...,sda8,sda9
	# "sda\]" -> "\" is for escaping "]" character
	# this cmd shows lines containing sda1 to sda9 but there may be some 
	# lines that have a sda1 to sda9 but they are in a parenthesis or bracket
```


## Regular Expression
It is a very powerful search engine but it's very hard to learn.

```
	man 7 regex # For more info in linux
```


	