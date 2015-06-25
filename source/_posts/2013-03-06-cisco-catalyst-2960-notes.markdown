---
layout: post
status: publish
published: true
title: Cisco Catalyst 2960 - Notes
author: DYURK
author_login: admin
author_email: null@dev.com
excerpt: ! "<h2>VLAN</h2>\r\n<h3>Creating VLANs</h3>\r\nShow all VLANs on switch\r\n<pre>&gt;
  sh vlan</pre>\r\nNow, Let's begin. Enter global configuration mode\r\n<pre># config
  t</pre>\r\nEnter a VLAN ID\r\n<pre># vlan 5</pre>\r\nProvide a name for the VLAN\r\n<pre>#
  name myvlan</pre>\r\nExit config\r\n<pre># end</pre>\r\n<h3>Assigning Ports to a
  VLAN</h3>\r\nEnter global configuration mode\r\n<pre># config t</pre>\r\nSelect
  the interface (port). Naming convention: Switch# / Port\r\n\r\ne.g Switch 1 port
  19\r\n<pre># interface Gi1/0/19</pre>\r\nDefine the VLAN membership mode for the
  port (Layer 2 access port).\r\n<pre># switchport mode access</pre>\r\nAssign the
  port to a VLAN\r\n<pre># switchport access vlan 5</pre>\r\nExit config\r\n<pre>#
  end</pre>\r\n<h2>"
wordpress_id: 694
wordpress_url: http://d87studios.com/blog/?p=694
date: 2013-03-06 03:07:46.000000000 -05:00
categories:
- Technology
- web operations
tags:
- cisco
- catalyst
- notes
comments: []
---
<h2>VLAN</h2>
<h3>Creating VLANs</h3>
Show all VLANs on switch
<pre>&gt; sh vlan</pre>
Now, Let's begin. Enter global configuration mode
<pre># config t</pre>
Enter a VLAN ID
<pre># vlan 5</pre>
Provide a name for the VLAN
<pre># name myvlan</pre>
Exit config
<pre># end</pre>
<h3>Assigning Ports to a VLAN</h3>
Enter global configuration mode
<pre># config t</pre>
Select the interface (port). Naming convention: Switch# / Port

e.g Switch 1 port 19
<pre># interface Gi1/0/19</pre>
Define the VLAN membership mode for the port (Layer 2 access port).
<pre># switchport mode access</pre>
Assign the port to a VLAN
<pre># switchport access vlan 5</pre>
Exit config
<pre># end</pre>
<h2><a id="more"></a><a id="more-694"></a></h2>
<h2>Back up and Restore Configuration Files</h2>
<h3>TFTP Back up</h3>
To back up the current configuration, enter Privilege Mode then type the following:
<pre>#copy running-config tftp:</pre>
You will then be prompt to provided the address of the tftp server &amp; the filename. Here is an example:
<pre>Address or name of remote host []? 102.10.15.44
 Destination filename [mco-confg]? name_of_config_file
 !!
 1030 bytes copied in 2.489 secs (395 bytes/sec)</pre>
<h3>TFTP Restore</h3>
To restore a configuration from a tftp server, first enter Privilege Mode then type the following:
<pre>#copy tftp: running-config</pre>
You will then be prompt to provided the address of the tftp server &amp; the filename. Here is an example:
<pre>Address or name of remote host []? 102.10.15.44
 Source filename []? backup_cfg_for_my_router
 Destination filename [running-config]?
 Accessing tftp://102.10.15.1/backup_cfg_for_my_router...
 Loading backup_cfg_for_router from 102.10.15.44 (via FastEthernet0/0): !
 [OK - 1030 bytes]</pre>
