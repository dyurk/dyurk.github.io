---
layout: post
status: publish
published: true
title: Batch File Collection
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 121
wordpress_url: http://d87studios.com/blog/?p=121
date: 2011-05-23 15:21:39.000000000 -04:00
categories:
- Additional Content
- Downloads
tags:
- batch file
- auto login
- domain
comments: []
---
<em>This page is setup as a place to archive past batch script that I have created. <strong>Please read before running any batch file</strong>. Use at your own risk!!  Also please note that this page is a work in progress, Thank You.</em>
<h2>Domain Related</h2>
<strong>Auto Log in Domain</strong> - Please edit lines 6-8, change DOMAIN_Name, USERNAME and PASSWORD
<pre class="wp-caption-dd">DefaultDomainName /t REG_SZ /d DOMAIN_NAME /f
DefaultUserName /t REG_SZ /d USERNAME /f
DefaultPassword /t REG_SZ /d PASSWORD /f</pre>
<strong><em> </em></strong><span style="color: #800000; background-color: #ffff99;"><em><a title="[DOWNLOAD]" href="http://d87studios.com/blog/wp-content/uploads/2011/05/AUTO_LOGIN_Domain.zip"><strong>[DOWNLOAD]</strong></a></em></span>

&nbsp;
<h2>Remote Actions<strong>
</strong></h2>
<strong>Remotely Shutdown Computers</strong> - Must be administrator to be able to run, must configure computer name
<pre class="wp-caption-dd">shutdown -s -f -m \\computername01 -c "TYPE MESSAGE HERE!"</pre>
<strong><em> </em></strong><span style="color: #800000; background-color: #ffff99;"><em><a title="[DOWNLOAD]" href="http://d87studios.com/blog/wp-content/uploads/2011/05/Shutdown_Computers.zip"><strong>[DOWNLOAD]</strong></a></em></span>

&nbsp;

<strong>Kill Task + Lock Computer</strong> [<strong>*</strong>] - Configure credentials and the process name.
<pre>taskkill /S computername01 /U administrator /P adminpass /IM taskname_whatever.exe
psshutdown -l \\computername01</pre>
<strong><em> </em></strong><span style="background-color: #ffff99;"><em><a title="[DOWNLOAD]" href="http://d87studios.com/blog/wp-content/uploads/2011/05/Killtask_lockcomputer.zip"><strong>[DOWNLOAD]</strong></a></em></span>

&nbsp;
<p class="wp-caption"><em><strong>*</strong>PsTools is need it to run this batch file. Download here: </em><a href="http://technet.microsoft.com/en-us/sysinternals/bb896649" target="_blank">http://technet.microsoft.com/en-us/sysinternals/bb896649</a></p>
