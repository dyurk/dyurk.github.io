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

[caption id="attachment_375" align="aligncenter" width="581" caption="mysqld.exe XN Resource Editor"]<a href="http://d87studios.com/blog/wp-content/uploads/2011/10/mysql-e1319210020404.png"><img class="size-full wp-image-375" title="mysqld.exe XN Resource Editor" src="http://d87studios.com/blog/wp-content/uploads/2011/10/mysql-e1319210020404.png" alt="mysqld.exe XN Resource Editor" width="581" height="493" /></a>[/caption]

&nbsp;

</div>
<ul>
	<li>Right click on "Language Natural" and click on <strong>Properties. </strong>A window will open, change the Language option to <strong>English (United States)</strong>.</li>
</ul>
<div>

[caption id="attachment_378" align="aligncenter" width="320" caption="Resource Properties"]<a href="http://d87studios.com/blog/wp-content/uploads/2011/10/mysql01.png"><img class="size-full wp-image-378" title="Resource Properties" src="http://d87studios.com/blog/wp-content/uploads/2011/10/mysql01.png" alt="Resource Properties" width="320" height="161" /></a>[/caption]

</div>
&nbsp;
<ul>
	<li>From the menu select <strong>Strings, </strong>and then <strong>Add String. </strong>It will create a default string with a 00000001 id.</li>
</ul>
<ul>
	<li>Opinally add the following string :</li>
</ul>
<pre style="text-align: center;"><span style="font-family: Consolas, Monaco, monospace;"><span class="Apple-style-span" style="font-size: 12px; line-height: 18px; white-space: pre;"><span class="wp-caption">%1For more information, see Help and Support Center at http://www.mysql.com.</span> </span></span></pre>
<ul>
	<li style="text-align: left;">Change the ID from '00000001' to:
<pre class="wp-caption"> 'C0000064'</pre>
</li>
</ul>
<ul>
	<li>Now Save and exit. Start MySql server now.</li>
</ul>
<div>That should do it. From now on you should see all the actual event messages in the Event Viewer.</div>
<div>Source: <a href="http://bugs.mysql.com/bug.php?id=48042">http://bugs.mysql.com/bug.php?id=48042</a></div>
<div></div>
<div></div>
<div></div>
