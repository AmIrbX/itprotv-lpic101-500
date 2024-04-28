Grub -> Grand Unified Boot loader

## What is Grub?
1. Grub stores boot information -> e.g location of operating system
2. Runs Before OS
3. Can call Microsoft windows boot loader as well (not a windows boot loader itself)



grub configuration location: `/etc/default/grub`
**We can change this file's content**

Grub Configuration Location 2: `/boot/grub.cfg`
**We as users can not change this file**

## How to change grub configuration?
```
	sudo nano /etc/default/grub
	sudo update-grub2 ## For updating grub's configuration folder
```
for custom changes it is **recommended** to write in this file:
```
	sudo nano /etc/grub.d/40_custom
```

