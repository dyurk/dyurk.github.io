---
layout: post
status: publish
published: true
title: Adding New Users in Nagios
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 482
wordpress_url: http://d87studios.com/blog/?p=482
date: 2012-04-04 18:21:33.000000000 -04:00
categories:
- Technology
- Linux
tags:
- nagios
- adding users
comments: []
---
To add new users for the web interface of Nagios you will need to run the following command:
<pre># htpasswd /usr/local/nagios/etc/htpasswd.users username01</pre>
Where "username01" is, type the name of the user you are trying to add. It will later prompt you for a password.

You will also need to edit your cgi configuration file.
<pre>authorized_for_system_commands=nagiosadmin,username01</pre>
<pre>authorized_for_all_services=nagiosadmin,username01</pre>
<pre>authorized_for_all_hosts=nagiosadmin,username01</pre>
<pre>authorized_for_all_service_commands=nagiosadmin,username01</pre>
<pre>authorized_for_all_host_commands=nagiosadmin,username01</pre>
Careful when editing the cgi config file. For security reasons you might not want to give full access to every user.
