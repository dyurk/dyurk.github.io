---
layout: post
status: publish
published: true
title: ! 'MySQL: The description for Event ID in Source cannot be found.'
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 373
wordpress_url: http://d87studios.com/blog/?p=373
date: 2011-10-21 15:37:35.000000000 -04:00
categories:
- Technology
tags:
- error
- server
- mysql
- event viewer
comments: []
---
If you keep getting this error in the Event Viewer you should do the following:
<p class="wp-caption">The description for Event ID ( 100 ) in Source ( MySQL ) cannot be found</p>
It seems like the local computer may not have the necessary registry information or message DLL files to display messages from a remote computer. We will have to use a program to edit the <strong>mysqld.exe </strong>to add the required information.
<ul>
	<li>Download XN Resource Editor - <a href="http://www.wilsonc.demon.co.uk/d10resourceeditor.htm">http://www.wilsonc.demon.co.uk/d10resourceeditor.htm</a></li>
</ul>
<ul>
	<li>Stop the MySql server.</li>
</ul>
<ul>
	<li>Locate and backup <strong>mysqld.exe - \</strong>MySQL Server\bin\mysqld.exe    <span style="color: #ff0000;"><em>Make sure to backup!!!!</em></span></li>
</ul>
<ul>
	<li>In XN Resource Editor open mysqld.exe and you should see both panes blank.</li>
</ul>
<ul>
	<li>From the menu select <strong>Resource, </strong>and then <strong>Add Resource. </strong>A window will open with a list of options, select <strong>Message Table.</strong></li>
</ul>
<div>

<a href="http://d87studios.com/blog/wp-content/uploads/2011/10/mysql-e1319210020404.png"><img class="size-full wp-image-375" title="mysqld.exe XN Resource Editor" src="http://d87studios.com/blog/wp-content/uploads/2011/10/mysql-e1319210020404.png" alt="mysqld.exe XN Resource Editor" width="581" height="493" /></a>

&nbsp;

</div>
<ul>
	<li>Right click on "Language Natural" and click on <strong>Properties. </strong>A window will open, change the Language option to <strong>English (United States)</strong>.</li>
</ul>
<div>

<a href="http://d87studios.com/blog/wp-content/uploads/2011/10/mysql01.png"><img class="size-full wp-image-378" title="Resource Properties" src="http://d87studios.com/blog/wp-content/uploads/2011/10/mysql01.png" alt="Resource Properties" width="320" height="161" /></a>

</div>
&nbsp;
From the menu select <strong>Strings, </strong>and then <strong>Add String. </strong>It will create a default string with a 00000001 id.

Change the ID from '00000001' to:
<pre> 'C0000064'</pre>

Now Save and exit. Start MySql server now.

<div>That should do it. From now on you should see all the actual event messages in the Event Viewer.</div>
<div>Source: <a href="http://bugs.mysql.com/bug.php?id=48042">http://bugs.mysql.com/bug.php?id=48042</a></div>
<div></div>
<div></div>
<div></div>
