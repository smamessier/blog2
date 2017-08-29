---
layout: post
title: Embed documents in your Ghost blog using ViewerJS and Express
date: '2016-03-06 23:25:09'
tags:
- dev-tutorials
---

Introduction
------------

Whether you are using Ghost as a blogging platform or to host your CV and research projects, it could come handy to embed documents such as PDF presentations or spreadsheets in a post. Embedding documents will  ensure that your readers don't have to download anything which will make their experience smoother. 

ViewerJS
--------

[ViewerJs](http://viewerjs.org/) is a javascript library making it easy to embed self-hosted documents in pages of your website. It uses Mozilla's well know [PDF.js](https://mozilla.github.io/pdf.js/) and KO's [WebODF](http://webodf.org/) under the hood. A ViewerJS plug-in is available for Wordpress but no such thing seems to exist to ease integration for Ghost bloggers.

Ghost and files
---------------

Ghost doesn't host documents for you as it does with post images. So we will have to setup our own simple file server. We will achieve this using the famous `Express` module for NodeJS.
#####Setting up a minimalistic file server

First your will need to download ViewerJS from their [GetIt page](http://viewerjs.org/getit/). From a Linux-based server, you can use the command line:
```bash
wget http://viewerjs.org/releases/ViewerJS-latest.zip
unzip ViewerJS-latest.zip  -d ViewerJS
```

Create a folder somewhere in your server and, and copy the ViewerJS folder inside.
```bash
mkdir docServer
cp -R ~/Downloads/ViewerJS/viewerjs-0.5.8/ViewerJS ./docServer/
cd docServer
```

Now that we are in `docServer` we can install the `NodeJS` module `Express` which will serve the ViewerJS library and the embedded documents.
```bash
npm install express
```

Finally we create a `server.js` file in which we put the minimalistic server code. (We picked 2375 but you can use any available port you want - preferably above 1024 so that you don't need sudo privileges to run it).
```javascript
var express = require('express');
var app = express();
app.use('/ViewerJS', express.static(__dirname + '/ViewerJS'));
app.use('/docs', express.static(__dirname + '/data'));
var server = app.listen(2375);
```

Let's now launch the server (We assume that you use [PM2](https://github.com/Unitech/pm2) to run Ghost on your production server - if not you should seriously think about it-.)
```bash
pm2 start server.js --name docServer
```

### Even better on port 80 
We assume that you have a Ghost blog proxied through a web server such as Nginx or Apache and that you have a certain level of privileges allowing to modify virtual host configuration files.

##### Apache
Modify your existing Ghost virtualhost to make it look like that:
```
 <VirtualHost *:80>
     ServerName yourghostblog.com
     ProxyPreserveHost on
     ProxyPass /docs/ http://localhost:2375/docs/
     ProxyPass /ViewerJS/ http://localhost:2375/ViewerJS/
     ProxyPass / http://localhost:2368/
</VirtualHost>
```

##### Nginx
ToDo

### Synchronizing files 
It is quite annoying to upload documents through ssh. To reduce the pain,you can use [Rsync](https://www.digitalocean.com/community/tutorials/how-to-use-rsync-to-sync-local-and-remote-directories-on-a-vps) (On Mac and Linux) to synchronize you documents between you local environment and the server host the Ghost blog.

##Conclusion
Here we go, you can now include embedded documents using ViewerJS instructions, i.e in a Ghost blog post, just use the following HTML
```
<iframe src = "/ViewerJS/#/docs/path/to/your/doc.pdf" width='100%' height='600' allowfullscreen webkitallowfullscreen></iframe> 
```

<iframe src = "/ViewerJS/#/docs/supaero/trex2A/trexTB20.pdf" width='100%' height='600' allowfullscreen webkitallowfullscreen></iframe> 

<object data="docs/supaero/trex2A/trexTB20.pdf" type="application/pdf" width="100%" height="100%">
  <p>It appears you don't have a PDF plugin for this browser.
  No biggie... you can <a href="myfile.pdf">click here to
  download the PDF file.</a></p>
</object>