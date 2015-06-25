---
layout: post
status: publish
published: true
title: ! 'Delete a single iptables rule '
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 494
wordpress_url: http://d87studios.com/blog/?p=494
date: 2012-06-07 13:00:44.000000000 -04:00
categories:
- Technology
- Linux
tags:
- Linux
- iptables
comments: []
---
This will list all of your rules, plus their chain name and number:
<pre lang="shell" prompt="$">iptables -vnL --line-numbers</pre>
Example:
<pre>10 14 898 ACCEPT tcp -- * * 0.0.0.0/0 0.0.0.0/0 state NEW tcp dpt:139 
11 54 3200 ACCEPT tcp -- * * 0.0.0.0/0 0.0.0.0/0 state NEW tcp dpt:445 
12 0 0 ACCEPT udp -- * * 0.0.0.0/0 0.0.0.0/0 state NEW udp dpt:137 
13 0 0 ACCEPT udp -- * * 0.0.0.0/0 0.0.0.0/0 state NEW udp dpt:138 
14 4 240 ACCEPT tcp -- * * 0.0.0.0/0 0.0.0.0/0 state NEW tcp dpt:22 
15 2344 325K REJECT all -- * * 0.0.0.0/0 0.0.0.0/0 reject-with icmp-host-prohibited</pre>
Let's say I want to remove the reject all rule, which is number 15.
<pre lang="shell" prompt="$">iptables -D INPUT 15</pre>
Now it's gone.
<pre>10 14 898 ACCEPT tcp -- * * 0.0.0.0/0 0.0.0.0/0 state NEW tcp dpt:139 
11 54 3200 ACCEPT tcp -- * * 0.0.0.0/0 0.0.0.0/0 state NEW tcp dpt:445 
12 0 0 ACCEPT udp -- * * 0.0.0.0/0 0.0.0.0/0 state NEW udp dpt:137 
13 0 0 ACCEPT udp -- * * 0.0.0.0/0 0.0.0.0/0 state NEW udp dpt:138 
14 4 240 ACCEPT tcp -- * * 0.0.0.0/0 0.0.0.0/0 state NEW tcp dpt:22</pre>
