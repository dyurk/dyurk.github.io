---
layout: post
status: publish
published: true
title: Netgear WG302 Firmware upgrade via Telnet
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 13
wordpress_url: http://d87studios.com/blog/?p=13
date: 2011-05-13 16:37:34.000000000 -04:00
categories:
- Technology
- Editors' Picks
tags:
- Netgear
- WG302
comments: []
---
<a href="http://kb.netgear.com/app/answers/detail/a_id/728">http://kb.netgear.com/app/answers/detail/a_id/728</a>

NOTE: Instead of using SolarWinds TFTP server i used  TFTPd32(<a href="http://tftpd32.jounin.net/">http://tftpd32.jounin.net/</a>)

<strong>Part 1: Upgrade the Boot Loader Commands:</strong>

1. Connect to the WG302 console port via MS Hyper terminal with these settings:
<ul>
	<li>Bits      per second: <strong>9600</strong></li>
	<li>Data      bits: <strong>8</strong></li>
	<li>Parity:      <strong>None</strong></li>
	<li>Stop      bits: <strong>1</strong></li>
	<li>Flow      control: None</li>
</ul>
<strong><img class="alignnone" title="Screen 1" src="http://kbserver.netgear.com/images/wg302_image001.gif" alt="" width="344" height="400" />
</strong>

2. Copy <strong>patch.txt</strong> from the zip file into a working file folder on your PC.

3. Connect the access point to your PC’s communication port with an RS232 cable.

4. After powering on the access point, immediately press <strong>CTRL-C (CTRL</strong> and <strong>C</strong> keys at the same time). The RedBoot&gt; prompt displays in HyperTerm. Here's an example of what this sequence might look like:

+Ethernet eth0: MAC address 00:09:5b:74:f3:c5

IP: 192.168.0.35/255.255.255.0, Gateway: 0.0.0.0
Default server: 192.168.0.36, DNS server IP: 0.0.0.0

RedBoot(tm) bootstrap and debug environment [ROM]

Red Hat certified release, version 1.92 - built 18:59:19, Sep 19 2003

Platform: IXDP425 Development Platform (XScale)

Copyright (C) 2000, 2001, 2002, Red Hat, Inc.

RAM: 0x00000000-0x10000000, 0x0001f920-0x0ffd1000 available

FLASH: 0x50000000 - 0x50800000, 64 blocks of 0x00020000 bytes each.

== Executing boot script in 2.000 seconds - enter ^C to abort

^C

RedBoot&gt;

5. Select <strong>Send Text File</strong> from <strong>Transfer</strong> Menu in HyperTerminal, and select <strong>patch.txt</strong> to transfer. The access point automatically rebots after upgrade is done.

6. Continue to Part 2 to upgrade the firmware.

<strong>Part 2: To Upgrade the Firmware Using TFTP</strong>

1. Configure the IP address of your PC to <strong>192.168.0.36</strong>. 2. If you do not have a TFTP server on your PC, install one now. (These are available, free, from such places as Solarwinds. You may download the software from http://support.solarwinds.net/updates/New-customerFree.) 3. Copy the WG302 firmware image: <strong>wg302_v4_1_8.rmt</strong> into the TFTP Root directory, such as c:TFTP-Root. 4. Rename the image to <strong>wg302.rmt</strong>. (If your TFTP server gives an error "ixp425.rmt not found" then you have a beta unit. For beta units rename "wg302.rmt" to ixp425.rmt.) 5. Connect your PC and the WG302 access point directly with a CAT5 Ethernet cable. 6. Start the TFTP server. (An example, showing Solarwinds start-up window, appears below.)

<img class="alignnone" title="2 Screen" src="http://kbserver.netgear.com/images/wg302_image003.gif" alt="" width="382" height="261" />

7. Disconnect the power cord from access point.

8. Press and hold the reset button on access point. Plug in the power while holding the reset button.

&nbsp;
