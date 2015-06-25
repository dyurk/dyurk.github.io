---
layout: post
status: publish
published: true
title: Wipe dalvik cache in Terminal, Andriod.
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 8
wordpress_url: http://d87studios.com/blog/?p=8
date: 2011-05-13 16:33:54.000000000 -04:00
categories:
- Technology
- Android
- Editors' Picks
tags:
- Android
- dalvik cache
comments: []
---
<em>*Root Required*</em>

Open your Terminal of choice and type the following.
<pre>$su
#cd /system/sd/dalvik-cache
#rm *
#exit
$exit</pre>
Reboot phone.
