---
layout: post
status: publish
published: true
title: Restored a cleared git stash
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 568
wordpress_url: http://d87studios.com/blog/?p=568
date: 2012-10-05 14:33:35.000000000 -04:00
categories:
- Linux
- git
tags:
- git
- stash
- restored
comments: []
---
Run the following:
<pre>git fsck --lost-found</pre>
You will get something similar to this:
<pre>Checking objects: 100% (6596/6596), done.
dangling commit e3b3b973asdasdasdasdasd7cqweqwe35f6d34e</pre>
Now just apply the stash's SHA1:
<pre>git stash apply e3b3b973asdasdasdasdasd7cqweqwe35f6d34e</pre>
