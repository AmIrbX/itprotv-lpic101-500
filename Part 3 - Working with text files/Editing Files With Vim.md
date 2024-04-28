
`Vim` and `Vi` are the same but the difference is that `Vim` is an extension of `Vi` and it's the improved version of `Vi` as the old text editor.

`Vim` has 3 modes:
1. Command Mode: issues commands like search and replace function
2. Insert Mode: for typing words 
3. Visual Mode: just read-only

**For Entering in Insert Mode -> Type `i`**
**For Entering in Command Mode -> Type `:`**
**For Entering in Visual Mode -> Press `ESC`**

- How to exit from vim modes -> Press `Esc` or `Ctrl + C`

#### How to go to a Certain Line Number?
```
	:1000 # Line Number
```

#### How to Delete a line?
```
	:d # Single Line
	:18,20d # Deletes lines 18,19,20 
```

#### How to Copy?
```
	# type (in Normal or visual mode):
	yy # Copy entire line
	3yy # Copy 3 lines starting from current line
	y$ # Copy everything from cursor to the rnd of the line (Y + SHIFT + 4)
	y^ # Copy everything from the cursor to the start of the line (Y + SHIFT + 6)
	yw # Copy to the start of the next word.
	yiw # Copy the current word.
	y% # Copy to the matching character. By default supported pairs are (), {}, []. (Y + SHIFT + 5)
```

#### How to Cut?
```
	dd # Delete (cut) the current line, including the newline character.
	3dd # Delete (cut) three lines, starting from the line where the cursor is positioned,
	d$ # Delete (cut) everything from the cursor to the end of the line.
	dw # Deletes to the start of the next word
	d^ # Deletes everything from the cursor to the start of the line (D + SHIFT + 6)
```


#### How to paste?
```
	p # Pastes the text AFTER the cursor
	P # Pastes the text BEFORE the cursor (SHIFT + P)
```

