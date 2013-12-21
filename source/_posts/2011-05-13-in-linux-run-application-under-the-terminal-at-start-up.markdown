---
layout: post
status: publish
published: true
title: In Linux; Run Application under the Terminal at start up.
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 23
wordpress_url: http://d87studios.com/blog/?p=23
date: 2011-05-13 16:42:07.000000000 -04:00
categories:
- Technology
- Linux
tags:
- Linux
comments: []
---
There are different ways to achieve this, but here is a simple way of doing it.

I created a new start up application under the Start Up Applications  Preferences, which is located under System&gt;Preferences&gt;Start Up  Applications.

<img src="../../images/pcmonitorclient1.PNG" alt="" />

&nbsp;

Here is the command that I placed in the command box:
<pre>gnome-terminal -e "java -Djava.library.path=/usr/share/pcmonitor/lib/ -jar /usr/share/pcmonitor/bin/pcmonitor.jar -c /usr/share/pcmonitor/etc/pcmonitor.conf &amp;" &amp;</pre>
&nbsp;

<img src="../../images/pcmonitorclient2.PNG" alt="" />

For my particular case, I'm trying out Mobile Pc Monitor which requires  to run a .Jar file.  But any other applications/commands can be used.
<pre>gnome-terminal -e "COMMAND IN HERE" &amp;</pre>
