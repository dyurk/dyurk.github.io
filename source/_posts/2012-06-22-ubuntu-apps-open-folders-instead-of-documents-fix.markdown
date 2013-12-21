---
layout: post
status: publish
published: true
title: Ubuntu apps open folders instead of documents fix
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 514
wordpress_url: http://d87studios.com/blog/?p=514
date: 2012-06-22 17:10:14.000000000 -04:00
categories:
- Uncategorized
- Technology
- Linux
tags:
- Ubuntu
- gnome-do
- xfec
comments:
- id: 1340
  author: ELshaima Kalifa
  author_email: sher3743@gmail.com
  author_url: http://www.facebook.com/elshaima.kalifa
  date: !binary |-
    MjAxMy0wMy0wOSAyMDoxNDowMCAtMDUwMA==
  date_gmt: !binary |-
    MjAxMy0wMy0wOSAyMDoxNDowMCAtMDUwMA==
  content: ! "ithink itis very god program \nto me thank u"
---
Recently after trying out Xfce I started to have issues with one of my go-to apps, Gnome Do. It would only open the directory of the file that i was trying to open. This also happen with Chrome, were downloaded files would not open, only their directory. The issue seems to be releated to some of the utilities that come with Xfec. This should do it:
<pre lang="shell" prompt="$">sudo apt-get remove exo-utils</pre>
