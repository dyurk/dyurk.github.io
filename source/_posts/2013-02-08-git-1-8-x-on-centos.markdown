---
layout: post
status: publish
published: true
title: git 1.8.x on CentOS
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 621
wordpress_url: http://d87studios.com/blog/?p=621
date: 2013-02-08 17:16:13.000000000 -05:00
categories:
- Uncategorized
- Technology
- Linux
- git
tags:
- Linux
- centos
- git
comments: []
---
At the moment this is not on EPEL &amp; CentOS repo, you'll have to compile from source.

Get the desired version: <a href="http://code.google.com/p/git-core/downloads/list">http://code.google.com/p/git-core/downloads/list</a>
<pre>tar -xzvf ./git-1.8.x.tar.gz</pre>
<pre>cd ./git-1.8.x</pre>
<pre id="crayon-51152fba206b0-5">./configure</pre>
<pre id="crayon-51152fba206b0-6">make &amp;&amp; make install</pre>
