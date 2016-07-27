# DServer 

This is a demo helper node js file to connect to server and add routes

How to use - <br>
1) Download folder dserver and place it on the root of your project <br>
2) Make app.js file <br>

var DS=require('./dserver');  // get dserver <br>
var fs=require('fs'); 
<br>
var ds=new DS();
<br>


ds.add('/',function(req,res)   //  add route for '/'  <br>
{
<br>
         res.writeHead(200,{'Content-Type':'text/html'}); <br>
          fs.createReadStream(__dirname+'/index.html').pipe(res); <br>
}); 

 <br>
//create server by giving port and host <br>
 <br>
ds.createServer(1337,'127.0.0.1'); <br>
