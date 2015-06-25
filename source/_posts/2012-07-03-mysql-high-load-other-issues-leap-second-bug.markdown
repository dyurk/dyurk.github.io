---
layout: post
status: publish
published: true
title: MySQL High Load / Other Issues - Leap second bug
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 519
wordpress_url: http://d87studios.com/blog/?p=519
date: 2012-07-03 01:28:25.000000000 -04:00
categories:
- Technology
- Linux
tags:
- Linux
- mysql
- lead second bug
- high cpu load
comments: []
---
After struggling with a sever that was acting up, i did some investigating and found it to be related to a recent leap second that was added on June 30th. On Saturday midnight Greenwich Mean Time (GMT), an extra second was added to the Universal Coordinated Time (UTC). According to some news reports the Linux kernel has a bug in how it handles leap seconds.

The fix was simple:
<pre lang="shell" prompt="$"> service ntpd stop
<br>date -s "`date`"
<br>service ntpd start</pre>
