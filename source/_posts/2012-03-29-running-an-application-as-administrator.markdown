---
layout: post
status: publish
published: true
title: Running an Application as Administrator
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 466
wordpress_url: http://d87studios.com/blog/?p=466
date: 2012-03-29 12:27:34.000000000 -04:00
categories:
- Technology
- Windows
tags:
- runas
- administrator
- windows
comments: []
---
If you find yourself working on a computer that is locked down and are in need of doing some tasks that required administrative privileges, the following command might be helpful. This can be done directly from the "RUN" command window.
<pre>runas /user:<span style="background-color: #ffff00;">Domain\Admin</span> "<span style="background-color: #ccffff;">C:\WINDOWS\explorer.exe</span> /separate"</pre>
Replace the yellow highlighted text with your own credentials. The credentials can be for a domain or a local admin user. The light-blue text represents the application you are trying to run with elevated rights.
