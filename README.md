# Useful scripts
## Find a file
```sh
#!/bin/sh

find / -name "*hede*" -print 2>/dev/null
```
#####

## Search for a string
```sh
#!/bin/sh

grep -r "hede" * 2>/dev/null
```
#####

## Find and delete files
```sh
#!/bin/sh

find . -name ".DS_Store*" -print 2>/dev/null |  xargs rm 

```
#####

## Find and delete files (in case of a space in path we should use)
```sh
#!/bin/sh

find . -name ".DS_Store*" -exec rm {} + 2>/dev/null 

```
