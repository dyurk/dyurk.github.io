---
layout: post
status: publish
published: true
title: Remotely view Internet browsing history
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 322
wordpress_url: http://d87studios.com/blog/?p=322
date: 2011-08-02 13:42:18.000000000 -04:00
categories:
- Technology
- Windows
tags:
- remote
- internet history
- utility
comments: []
---
As a Sysadmin you are sometimes force to do some detective work, and 90% of the time this will involve the auditing of user's browsing history. There are many utilities out there, but i wanted to shared IE History View, a long time favorite app I constantly use.

[caption id="attachment_332" align="aligncenter" width="300" caption="IE History View Screenshot"]<a href="http://d87studios.com/blog/wp-content/uploads/2011/08/iehistory1.png"><img class="size-medium wp-image-332" title="IE History View Screenshot " src="http://d87studios.com/blog/wp-content/uploads/2011/08/iehistory1-300x246.png" alt="IE History View Screenshot" width="300" height="246" /></a>[/caption]

Each time that you type a URL in the address bar or click on a link in Internet Explorer browser, the URL address is automatically added to the history index file, and this utility reads all information from the history file and displays the list of all URLs that the user has visited in the last few days.

One of the great advantages of IE History View is that it is a portable application and there is no need for installation. The application can be run locally to audit the local computer and all the local users or it can be used to remotely audit a computer in your network.
<h1>Remotely view internet activity</h1>
Go to File-Select History Folder. This window will open up:

[caption id="attachment_328" align="aligncenter" width="466" caption="IE History Viewer: Select History Folder"]<a href="http://d87studios.com/blog/wp-content/uploads/2011/08/iehistory2.png"><img class="size-full wp-image-328" title="IE History Viewer: Select History Folder" src="http://d87studios.com/blog/wp-content/uploads/2011/08/iehistory2.png" alt="IE History Viewer: Select History Folder" width="466" height="261" /></a>[/caption]

In this window you will need to specify the computer name and the local user account name. It has to be done in this format:
<pre class="wp-caption">\\<span style="color: #ff6600;">COMPUTER</span>\c$\Documents and Settings\<span style="color: #ff6600;">USER</span>\Local Settings\History</pre>
That should be everything, now you should be able to get a fully detail list of the browsing history of the user.

Let's not forget to give credit to Nir Sofer the creator of this great utility. Please check his website: <a href="http://www.nirsoft.net/utils/iehv.html">http://www.nirsoft.net/utils/iehv.html</a>

&nbsp;
