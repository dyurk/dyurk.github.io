---
layout: post
status: publish
published: true
title: ! 'Configuring memcached '
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 610
wordpress_url: http://d87studios.com/blog/?p=610
date: 2013-01-11 16:45:26.000000000 -05:00
categories:
- Technology
- Linux
- web operations
tags:
- memcached
comments: []
---
<h3>What is memcached?</h3>
memcached is a high-performance, distributed memory object caching system, generic in nature, but originally intended for use in speeding up dynamic web applications by alleviating database load.
<h3>Configuring memcached</h3>
Edit
<pre>/etc/sysconfig/memcached</pre>
Sample configuration. Cache size is important, it determines the amount of ram in megabytes that are allocated to memcached pool.
<pre>PORT="11211"
USER="memcached"
MAXCONN="1024"
CACHESIZE="12288"
OPTIONS=""</pre>
