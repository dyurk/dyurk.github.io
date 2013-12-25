---
layout: post
status: publish
published: true
title: Apache Proxy Example
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 663
wordpress_url: http://d87studios.com/blog/?p=663
date: 2013-03-12 16:58:56.000000000 -04:00
categories:
- Technology
- web operations
tags:
- apache
- httpd
- proxy
comments: []
---
Apache proxy example for web app running on myapp.website.com on port 7990.

```apacheconf
<VirtualHost *:80>
        ServerName myapp.website.com
        ProxyRequests Off

        <Proxy *>
                Order deny,allow
                Allow from all
        </Proxy>

                # Logging
        LogFormat "%h %l %u %t \"%r\" %>s %b" common
        CustomLog logs/access_log common


        ProxyTimeout    7200
        ProxyPreserveHost On
        ProxyPass           /       http://localhost:7990/
        ProxyPassReverse    /       http://localhost:7990/
        ProxyTimeout     86400

</VirtualHost>

```
