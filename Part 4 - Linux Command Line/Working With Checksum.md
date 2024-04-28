We use `Checksum` for validating a file to know whether it is compromised or not

First we want to know which `Checksum` algorithms we can use:
```
	ls /usr/bin/*sum
```

These are the most common algorithms that a developer or a vendor might use:
```
	sha256sum
	sha512sum
	sha128sum
```

## How to use `checksum`:
```
	sha256sum filename.txt

	checksum                         filename
```

### Checking multiple files's `checksum`?
```
	sha256sum --check checksums.txt
```

`checksums.txt` is a file that most vendors provide that contains of the file name 
and the `checksum`. `sha256sum` and other algorithms's binary recognize that pattern.

```
SHA256SUM (filename.extension) = checksum
```



