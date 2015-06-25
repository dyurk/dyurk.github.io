---
layout: post
status: publish
published: true
title: Examples of lftp
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 548
wordpress_url: http://d87studios.com/blog/?p=548
date: 2012-08-09 13:14:25.000000000 -04:00
categories:
- Technology
- Linux
tags:
- bash
- lftp
comments: []
---
In this example we are changing directory to "output" and doing a listing of files:
<pre> lftp -e 'set net:timeout 10;cd output/;ls; bye' -u USER,PASSWORD ftp.foo.com/</pre>
Here we are going to "output" and we transferring "myfile.txt" to our local /tmp directory.
<pre>lftp -e 'set net:timeout 10;cd output/;get myfile.txt -o /tmp/; bye' -u USER,PASSWORD ftp.foo.com/</pre>
