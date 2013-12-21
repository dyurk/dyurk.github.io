---
layout: post
status: publish
published: true
title: ! 'su apache: "This account is currently not available"'
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 561
wordpress_url: http://d87studios.com/blog/?p=561
date: 2012-09-11 16:04:27.000000000 -04:00
categories:
- Uncategorized
tags:
- bash
- shell
- su
- apache
- chsh
comments: []
---
When trying to switch user to apache and you get the following: "This account is currently not available". You need to set a shell for the apache user. Let's say we want to use bash.
<pre># chsh -s /bin/bash apache

</pre>
You should get this prompt:
<pre>Changing shell for apache.
Shell changed.</pre>
Done! Now you should be able to su as apache.
