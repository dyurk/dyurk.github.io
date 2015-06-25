---
layout: post
status: publish
published: true
title: ERROR 2006 (HY000) MySQL server has gone away
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 645
wordpress_url: http://d87studios.com/blog/?p=645
date: 2013-02-20 22:08:22.000000000 -05:00
categories:
- web operations
tags:
- error
- mysql
- max_allowed_packet
comments: []
---
The server's default <a href="http://dev.mysql.com/doc/refman/5.5/en//server-system-variables.html#sysvar_max_allowed_packet"><code>max_allowed_packet</code></a> value is 1MB and it looks like it has exceeded the default max. You can increase this if the server needs to handle big queries. This can be done in two ways:

Start MySQL client with the following option (64 MB for this example)
<pre><code>mysql --max_allowed_packet=64M </code></pre>
or Add the following in your my.cnf file
<pre><code>max_allowed_packet=64M</code></pre>
