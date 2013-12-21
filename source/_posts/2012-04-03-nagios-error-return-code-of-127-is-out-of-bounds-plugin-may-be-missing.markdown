---
layout: post
status: publish
published: true
title: ! 'Nagios Error: “Return code of 127 is out of bounds – plugin may be missing” '
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 473
wordpress_url: http://d87studios.com/blog/?p=473
date: 2012-04-03 13:12:04.000000000 -04:00
categories:
- Technology
- Linux
tags:
- Linux
- nagios
- snmp
- net-snmp
comments: []
---
If you are monitoring network devices in Nagios and you get the following error:

<address><strong> “Return code of 127 is out of bounds – plugin may be missing” </strong></address>Most likely you are missing some SNMP packages. Make sure you have the following:
<pre>net-snmp-libs-x.x.x
net-snmp-x.x.x
net-snmp-utils-x.x.x</pre>
Run this command to make sure that you don't have them:

For RHEL\CentOS\Fedora:
<pre>rpm -qa | grep net-snmp</pre>
For Debian based distros:
<pre>dpkg --get-selections | grep net-snmp</pre>
If the command does not return anything, then you are missing all three packages. Proceed to install them using your package manager.

After you are done verify that the packages are installed:
<pre># rpm -qa | grep net-snmp
 net-snmp-libs-5.5-37.el6_2.1.i686
 net-snmp-5.5-37.el6_2.1.i686
 net-snmp-utils-5.5-37.el6_2.1.i686</pre>
One last step. You will need to stop Nagios to recompile and re-install the Nagios Plug-ins.

Go to the folder where the plug-ins are downloaded.
<pre> /configure --with-nagios-user=nagios --with-nagios-group=nagios</pre>
<pre> Make</pre>
<pre> Make Install</pre>
<pre> service nagios start</pre>
