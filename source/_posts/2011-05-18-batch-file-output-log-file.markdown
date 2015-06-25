---
layout: post
status: publish
published: true
title: Batch file output to Log file
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 83
wordpress_url: http://d87studios.com/blog/?p=83
date: 2011-05-18 15:24:55.000000000 -04:00
categories:
- Technology
- Windows
tags:
- scripts
- batch file
- log
- automated
comments: []
---
When running a batch file it might be beneficial and necessary to have a log file detailing the status of the commands. While there are different ways around creating a log file, batch file redirection is the key.

To explain redirection lets see this example of a batch file that shutdowns some computers:
<blockquote>shutdown -s -f -m \\Computer01 -c  <strong>&gt;&gt; shutdownlog.txt 2&gt;&amp;1</strong>

shutdown -s -f -m \\Computer02 -c  <strong>&gt;&gt; shutdownlog.txt 2&gt;&amp;1</strong>

shutdown -s -f -m \\Computer03 -c <strong> &gt;&gt; shutdownlog.txt 2&gt;&amp;1</strong></blockquote>
If you look at the end of the command i have added the following:

<strong>&gt;&gt;</strong> - Will append the log file.

<strong>shutdownlog.txt -</strong>The name given to the log file.

<strong>2&gt;&amp;1 </strong>- Displays standard output and standard error of command on the log file.

At the end of your batch file you can also add a date &amp; time stamp:
<blockquote>echo %date% %time% &gt;&gt; shutdownlog.txt</blockquote>
Great page on Batch file redirection - http://www.robvanderwoude.com/redirection.php
