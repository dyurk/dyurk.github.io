---
layout: post
status: publish
published: true
title: Some Client computers do not appear in the WSUS console
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 206
wordpress_url: http://d87studios.com/blog/?p=206
date: 2011-06-07 20:33:03.000000000 -04:00
categories:
- Technology
- Windows
tags:
- WSUS
- windows update
- server
- windows server
- ad
- gpo
- client
- active directory
comments: []
---
There are many reasons why some clients might not appear in the WSUS console. For example, GPO errors, a corrupt installation on the server or client side and issues with IIS  just to name a few.

Many of these issues can be pinpointed by running the WSUS Client Diagnostic Tool and if necessary the Server Diagnostic Tool. Both of these tools can be downloaded here: <strong><a href="http://technet.microsoft.com/en-us/windowsserver/bb466192.aspx">http://technet.microsoft.com/en-us/windowsserver/bb466192.aspx</a></strong>

<a href="http://d87studios.com/blog/wp-content/uploads/2011/06/wsus_client_diag.png"><img class="size-full wp-image-211  " title="WSUS Client Diagnostic Tool" src="http://d87studios.com/blog/wp-content/uploads/2011/06/wsus_client_diag.png" alt="WSUS Client Diagnostic Tool" width="577" height="422" /></a>

Usually when adding a new computer to your domain, if you have a correct Group Policy set in place you should see that computer show up in the WSUS console. Also if you want to force the issue you can open the command prompt and type the following:
<pre><strong>net start wuauserv</strong></pre>
<pre><strong>wuauclt /detectnow</strong></pre>
<h2>Active Directory Container</h2>
Recently while setting up some new computers, i ran through a problem where some computers were missing in the WSUS console. It was kind of random since some of the computers where showing, while a selected few were missing. I double checked that the computers had properly joined the domain, i ran "<em>gpupdate /f" </em>and they still could not be found.

I decided to check under Active Directory and i found out that my new computers and others that where not showing up in the WSUS console where on the wrong container.

<a href="http://d87studios.com/blog/wp-content/uploads/2011/06/Active_Directory.png"><img class="size-full wp-image-214" title="Active Directory Containers " src="http://d87studios.com/blog/wp-content/uploads/2011/06/Active_Directory.png" alt="Active Directory Containers " width="595" height="518" /></a>

My new computer was in the "Computers" container and after moving it to our "default" container where the original policy was set, i was able to see the computer on WSUS console.

&nbsp;

