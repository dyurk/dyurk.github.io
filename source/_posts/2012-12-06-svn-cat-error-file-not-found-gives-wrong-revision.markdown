---
layout: post
status: publish
published: true
title: ! 'SVN cat error: "File not found". Gives wrong revision'
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 564
wordpress_url: http://d87studios.com/blog/?p=564
date: 2012-12-06 02:47:02.000000000 -05:00
categories:
- Linux
- Subversion
tags:
- svn
comments: []
---
You will need to use the peg revision

svn <em><code>command</code></em> -r <em><code>OPERATIVE-REV</code></em> item@<em><code>PEG-REV</code></em>

http://svnbook.red-bean.com/en/1.2/svn.advanced.pegrevs.html
