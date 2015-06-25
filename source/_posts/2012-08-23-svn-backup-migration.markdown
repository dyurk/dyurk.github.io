---
layout: post
status: publish
published: true
title: ! 'SVN Backup & Migration '
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 558
wordpress_url: http://d87studios.com/blog/?p=558
date: 2012-08-23 16:00:34.000000000 -04:00
categories:
- Technology
- Linux
tags:
- svn
- backup
- migrations
- svnadmin
comments:
- id: 1323
  author: Ron7st0d
  author_email: whitel@try.net
  author_url: ''
  date: !binary |-
    MjAxMi0xMi0xNSAxOToxMTowMCAtMDUwMA==
  date_gmt: !binary |-
    MjAxMi0xMi0xNSAxOToxMTowMCAtMDUwMA==
  content: excellent!
---
<h2>Backing Up</h2>
Backing up the D87 repo:
<pre># svnadmin dump /var/svn/repos/D87 &gt; D87_repo.svndump</pre>
<h2>Migrating a Repository</h2>
First back up the Repo (See steps above). Now create the repo in the new location.

e.g. D87 repo:
<pre># svnadmin create /var/svn/repos/D87</pre>
Load the dump file created during the backup process
<pre># svnadmin load /var/svn/repos/D87 &lt; D87_repo.svndump</pre>
