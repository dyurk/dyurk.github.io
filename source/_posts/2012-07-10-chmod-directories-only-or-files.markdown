---
layout: post
status: publish
published: true
title: chmod directories and files separately
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 522
wordpress_url: http://d87studios.com/blog/?p=522
date: 2012-07-10 01:28:42.000000000 -04:00
categories:
- Uncategorized
- Technology
- Linux
tags:
- Linux
- chmod
- find
comments: []
---
If you are looking to chmod directories and files separately, the <em>find</em> command can be of great help. Take a look at these examples:

For Directories:
<pre lang="shell" prompt="$">find . -type d -exec chmod -v 775 {} \;</pre>
For Files:
<pre lang="shell" prompt="$">find . -type f -exec chmod -v 664 {} \;</pre>
