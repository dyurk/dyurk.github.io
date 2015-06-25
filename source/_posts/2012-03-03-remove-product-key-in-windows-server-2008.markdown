---
layout: post
status: publish
published: true
title: Remove Product Key in Windows Server 2008
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 413
wordpress_url: http://d87studios.com/blog/?p=413
date: 2012-03-03 18:40:40.000000000 -05:00
categories:
- Technology
- Windows
tags:
- windows server
- product key
comments: []
---
To remove the current product key in your Server 2008 installation follow these simple steps:

Open the command promp
<p style="padding-left: 30px;">START &gt; Run &gt; type "<em>cmd</em>"</p>
Navigate to the system32 folder
<p style="padding-left: 30px;"><em>path: C:\Windows\system32</em></p>
Type the following:
<pre style="padding-left: 30px;">slmgr.vbs -upk</pre>
Wait a few seconds and a window will popup confirming the removal of the product key.
