---
layout: post
status: publish
published: true
title: Safely remove archived updates/hotfixes from Windows Server 2008 & Windows
  7
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 433
wordpress_url: http://d87studios.com/blog/?p=433
date: 2012-03-07 14:02:13.000000000 -05:00
categories:
- Technology
- Windows
- Editors' Picks
tags:
- windows server
- Clean Tool
- COMPCLN
- DISM
comments: []
---
In a event where you are running low on disk space after applying a service pack or a set of updates, there are two unique tools that can be used to safely remove some of the archived information that is set aside by Windows.

The two tools that can be used for Windows Server 2008 are <strong><a href="http://technet.microsoft.com/en-us/library/dd351467(v=ws.10).aspx#BKMK_COMPCLN" target="_blank">COMPCLN</a></strong> and <strong><a href="http://technet.microsoft.com/en-us/library/dd744382(v=ws.10).aspx" target="_blank">DISM</a>.</strong> COMPCLN is the older utility that's been around since Vista, and it is recommended that you run DISM instead. Either way both commands seem to do the same function. <em>Please note that COMPCLN does not work in Windows 7.</em>
<h2>DISM Command</h2>
<a href="http://d87studios.com/blog/wp-content/uploads/2012/03/dism.png"><img class="size-full wp-image-435" title="dism" src="http://d87studios.com/blog/wp-content/uploads/2012/03/dism.png" alt="" width="677" height="342" /></a>

There are many switches when running this command and is recommended that you look into all the options in the <a href="http://technet.microsoft.com/en-us/library/dd744382(v=ws.10).aspx" target="_blank">Microsoft manual</a>. For the most part the command should look like this:
<pre>dism /online /cleanup-image /spsuperseded</pre>
Upon completion, you will not be able to remove any service packs that were installed, since they are now permanent in the OS.

&nbsp;

&nbsp;
