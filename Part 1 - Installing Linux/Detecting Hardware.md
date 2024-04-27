Interaction of user and driver:
User -> Software -> Kernel -> Drivers

Kernel interacts with drivers (Calls them) with `ubus` service.

Commands:
`lspci` -> lists all recognized PCI devices 
`lsusb` -> lists all recognized USB devices
`lsmod` -> lists all installed Modules
`rmmod` -> Removes a module (Temporary)


---

## How to know wheather a device has been recognized or not?

1- If recognized -> the device will have a name
2- if NOT recognized -> will NOT have a name -> missing a Driver


## Where are hardware drivers located?

**There are some placeholders for devices that may be connected to the system.**

## What is the service that gives name to the drivers?
`udev` service 

`udev` service config files:
`/etc/udev/` -> if empty it means udev is using the default names.
	`udev.conf
	`rules.d` 

**Better Not to change the naming rules**

## How to remove a module permanently?
There is a service called `modprob.d` that is responsible for probing or scanning new devices connected and finding and installing the relevent. If we want to permanently remove a module we should put the name of it in blacklist so the kernel don't power them on.
**How?**

```
cd \etc\modprobe.d
nano blacklist.conf
	blacklist name_of_module
```

**Linux Ecosystem -> Drivers = Modules**


