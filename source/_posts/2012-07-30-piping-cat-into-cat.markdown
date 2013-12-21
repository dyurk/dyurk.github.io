---
layout: post
status: publish
published: true
title: piping CAT into CAT
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 542
wordpress_url: http://d87studios.com/blog/?p=542
date: 2012-07-30 15:30:07.000000000 -04:00
categories:
- Technology
- Linux
tags:
- cat
comments: []
---
Let's say we have two files, <em>A.txt</em> &amp; <em>B.txt</em>. To show the output of these two files at once you will need to pipe cat using a "-".
<pre>cat a.txt | cat - b.txt</pre>
&nbsp;
