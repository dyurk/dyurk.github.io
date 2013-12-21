---
layout: post
status: publish
published: true
title: history command with date and timestamp
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 497
wordpress_url: http://d87studios.com/blog/?p=497
date: 2012-06-14 00:38:25.000000000 -04:00
categories:
- Technology
- Linux
tags:
- history
- bash
- timestamp
comments: []
---
You can get a more detailed display of your bash history by including the date and timestamps. This can be done by defining an environmental variable.
<pre lang="shell" prompt="$">HISTTIMEFORMAT="%d/%m/%y %T"</pre>
After defining this variable your bash history should look like this<em>:</em>
<pre lang="shell"> 963 13/06/12 20:14:39 ls
 964 13/06/12 20:14:43 cd models/
 965 13/06/12 20:14:44 ls
 966 13/06/12 20:14:53 git pull
 967 13/06/12 20:15:05 git push</pre>
