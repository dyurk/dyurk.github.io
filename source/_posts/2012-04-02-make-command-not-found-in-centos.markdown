---
layout: post
status: publish
published: true
title: Make Command Not Found in CentOS
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 470
wordpress_url: http://d87studios.com/blog/?p=470
date: 2012-04-02 14:45:43.000000000 -04:00
categories:
- Technology
- Linux
tags:
- centos
- make command
- yum
comments: []
---
If you are getting this error, you will need to install the gcc automake. Type the following command:
<pre>yum -y install gcc automake autoconf libtool make</pre>
That's it!
