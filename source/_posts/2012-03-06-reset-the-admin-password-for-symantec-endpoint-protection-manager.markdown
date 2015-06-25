---
layout: post
status: publish
published: true
title: Reset the admin password for Symantec Endpoint Protection Manager
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 424
wordpress_url: http://d87studios.com/blog/?p=424
date: 2012-03-06 13:22:07.000000000 -05:00
categories:
- Uncategorized
- Technology
- Windows
- Editors' Picks
tags:
- symantec
- reset password
- endpoint
comments: []
---
<a href="http://d87studios.com/blog/wp-content/uploads/2012/03/symantec_enpoint_manager.png"><img class="size-full wp-image-430" title="symantec_enpoint_manager" src="http://d87studios.com/blog/wp-content/uploads/2012/03/symantec_enpoint_manager.png" alt="" width="552" height="450" /></a>

You can use the resetpass.bat tool to reset the user name and password for the account that you use to log on to Symantec Endpoint Protection Manager. If the user name or password is something other than admin, running resetpass.bat changes the user name and password back to admin.
<p class="wp-caption">Note: If the account has been locked out due to repeated logon attempts, the resetpass.bat tool does not unlock the account. The default lockout period is 15 minutes.</p>
<strong>To reset the administrator password</strong>
<ol>
	<li>Open Windows Explorer on the computer that runs Symantec Endpoint Protection Manager.</li>
	<li>Locate the Drive:\Program Files\Symantec\Symantec Endpoint Protection Manager\Tools folder.</li>
	<li>Double-click resetpass.bat. The user name and password are reset to admin.</li>
	<li>Log on to Symantec Endpoint Protection Manager using admin for both the user name and the password, and change the password.</li>
</ol>
<a href="http://d87studios.com/blog/wp-content/uploads/2012/03/symantec_reset_pass.png"><img class="size-full wp-image-429" title="symantec_reset_pass" src="http://d87studios.com/blog/wp-content/uploads/2012/03/symantec_reset_pass.png" alt="" width="417" height="267" /></a>
