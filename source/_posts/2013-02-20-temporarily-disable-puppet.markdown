---
layout: post
status: publish
published: true
title: Temporarily Disable Puppet
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 642
wordpress_url: http://d87studios.com/blog/?p=642
date: 2013-02-20 21:26:26.000000000 -05:00
categories:
- Technology
- Linux
- web operations
tags:
- puppet
comments: []
---
This is can be done by an admin disabled of Puppet
<pre># puppet agent --disable "Reason why disabled"</pre>
To make sure it's disable, just do a Puppet run;
<pre># puppet agent -t
 Notice: Skipping run of Puppet configuration client; administratively disabled (Reason: 'Testing some new things');
 Use 'puppet agent --enable' to re-enable.</pre>
To enable:
<pre>puppet agent --enable</pre>
