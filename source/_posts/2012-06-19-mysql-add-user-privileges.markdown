---
layout: post
status: publish
published: true
title: ! 'MySQL: Add User + Privileges '
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 507
wordpress_url: http://d87studios.com/blog/?p=507
date: 2012-06-19 01:24:41.000000000 -04:00
categories:
- Technology
- Linux
tags:
- mysql
- privileges
- grant all
comments: []
---
Let's say we want to add a new user "Erick Broski" with SELECT privileges on database "userlistdb".
<pre>mysql&gt; grant SELECT on userlistdb.* to 'erick.broski'@'localhost';</pre>
Make sure to set his password:
<pre>mysql&gt; set password for 'erick.broski'@'localhost'= password('h@ckm3');</pre>
Now, lets say we want to give "Erick Broski" all privileges on database "ssnumbersdb".
<pre>mysql&gt; grant ALL PRIVILEGES on ssnumbersdb.* to 'erick.broski'@'localhost';</pre>
Additionally, we can limit the access to a DB by the user's IP.
<pre> mysql&gt; RENAME USER 'erick.broski'@'localhost' TO 'erick.broski'@'192.168.%';</pre>
Show all users.
<pre>mysql&gt; SELECT user FROM mysql.user;</pre>
&nbsp;

&nbsp;
