---
layout: post
status: publish
published: true
title: Redirect all HTTP request to HTTPS
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 678
wordpress_url: http://d87studios.com/blog/?p=678
date: 2012-03-13 13:57:54.000000000 -04:00
categories:
- Technology
- Linux
- web operations
tags:
- apache
- httpd
- ssl
- https
- vhost
comments: []
---

```
<VirtualHost *:80>
       ServerAlias *
       RewriteEngine On
       RewriteRule ^(.*)$ https://%{HTTP_HOST}$1 [redirect=301]
</VirtualHost>
```
