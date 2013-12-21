---
layout: post
status: publish
published: true
title: Upgrading Domain Controllers from Windows Server 2003 to 2008
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 420
wordpress_url: http://d87studios.com/blog/?p=420
date: 2012-03-04 13:56:08.000000000 -05:00
categories:
- Technology
- Windows
tags:
- windows server
- active directory
- upgrade
comments: []
---
When looking to upgrade your Active Directory system and Domain Controllers from a Windows Server 2003 to 2008, you will need to go over the <a title="AD Upgrade Checklist" href="http://technet.microsoft.com/en-us/library/cc753147(v=ws.10).aspx" target="_blank">Checklist</a> provided by Microsoft. One of the first steps in the checklist consist of preparing your environment to properly work with 2008. The following command will prepare your current AD and DC.

Load the Windows Server 2008 installation cd &amp; navigate to adprep folder via comand promp: <strong>D:\sources\adprep</strong>

Now run the following command, which will prepare the forest schema:
<pre>adprep /forestprep</pre>
[caption id="attachment_421" align="aligncenter" width="699" caption="adprep command"]<a href="http://d87studios.com/blog/wp-content/uploads/2012/03/upgrade_03-08.png"><img class="size-full wp-image-421" title="adprep" src="http://d87studios.com/blog/wp-content/uploads/2012/03/upgrade_03-08.png" alt="" width="699" height="348" /></a>[/caption]

&nbsp;

We will also need to run another command:
<pre>adprep /domainprep /gpprep</pre>
[caption id="attachment_422" align="aligncenter" width="703" caption="domainprep command"]<a href="http://d87studios.com/blog/wp-content/uploads/2012/03/upgrade_03-08_1.png"><img class="size-full wp-image-422" title="domainprep" src="http://d87studios.com/blog/wp-content/uploads/2012/03/upgrade_03-08_1.png" alt="" width="703" height="349" /></a>[/caption]
