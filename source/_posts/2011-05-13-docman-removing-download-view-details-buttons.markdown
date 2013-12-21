---
layout: post
status: publish
published: true
title: DOCMan; Removing "Download", "View" & "Details" Buttons
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 5
wordpress_url: http://d87studios.com/blog/?p=5
date: 2011-05-13 16:32:24.000000000 -04:00
categories:
- Technology
tags: []
comments: []
---
Go to <strong>/components/com_docman/themes/default/templates/documents/tasks.tpl.php</strong>

Replace everything on line 37 and below with this code:
<pre>foreach($this-&gt;doc-&gt;buttons as $button) {
$popup = ($button-&gt;params-&gt;get('popup', false)) ? 'type="popup"' : '';
$attr = '';
if($class = $button-&gt;params-&gt;get('class', '')) {
$attr = 'class="' . $class . '"';
}
$skip = array("Download","View","Details");  // &lt;-- add list of buttons
if (in_array($button-&gt;text,$skip)) CONTINUE; // &lt;-- skip "echo" if in list    ?&gt;&lt;li &lt;?php echo $attr?&gt;&gt;
&lt;a href="/&lt;?php echo $button-&gt;link?&gt;" &lt;?php echo $popup?&gt;&gt;
&lt;?php echo $button-&gt;text ?&gt;
&lt;/a&gt;
&lt;/li&gt;&lt;?php
}</pre>
&nbsp;

You might also want to remove that annoying white space left off. To do this go to:

<strong>/components/com_docman/themes/default/css/theme.css</strong>

Replace line 177-185 with this:

<span style="font-family: Consolas, Monaco, 'Courier New', Courier, monospace; font-size: 12px; line-height: 18px; white-space: pre;">.dm_taskbar {</span>
<pre>height: 0px;
padding-bottom:0px;
margin-bottom:0px;
/*border-bottom: 1px solid #bbb;*/
font-family: arial;
list-style-type: none;
}</pre>
