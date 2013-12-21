---
layout: post
status: publish
published: true
title: ! 'Puppet: Adding a Package '
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 545
wordpress_url: http://d87studios.com/blog/?p=545
date: 2012-08-09 13:04:08.000000000 -04:00
categories:
- Technology
- Linux
tags:
- puppet
comments: []
---
For this example lets ensure we have lftp install.

<pre>package { "lftp":
        ensure =&gt; "latest"
}</pre>
