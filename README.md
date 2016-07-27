# DServer 

This is a demo helper node js file to connect to server and add routes

How to use -
1) Download folder dserver and place it on the root of your project
2) Make app.js file

var DS=require('./dserver');  // get dserver
var fs=require('fs');
var ds=new DS();


ds.add('/',function(req,res)   //  add route for '/' 
{
         res.writeHead(200,{'Content-Type':'text/html'});
          fs.createReadStream(__dirname+'/index.html').pipe(res);
});

//create server by giving port and host

ds.createServer(1337,'127.0.0.1');
