---
layout: post
status: publish
published: true
title: Terminal Service Printers do not keep local settings.
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 362
wordpress_url: http://d87studios.com/blog/?p=362
date: 2011-08-18 16:07:15.000000000 -04:00
categories:
- Technology
- Windows
tags:
- terminal service
- printer
comments: []
---
<h3>The Problem:</h3>
When you start a Terminal Services session with a local printer, a redirected print queue is created in the Terminal Services session. All of your settings should be transfer over to the redirected printer, but that is not the case all the time. Some printing models do not support detecting changes to the Device Settings tab for each redirected printer.
<h3>The Solution:</h3>
The solution is to make the desired change in the Device Settings tab and then change a different setting in another tab, then hit Apply. This is all done inside the terminal session.

Source: <a href="http://support.microsoft.com/default.aspx?scid=KB;EN-US;243942">http://support.microsoft.com/default.aspx?scid=KB;EN-US;243942</a>
