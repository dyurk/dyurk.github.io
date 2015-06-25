---
layout: post
status: publish
published: true
title: The execution of scripts is disabled on this system; error in PowerShell
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 61
wordpress_url: http://d87studios.com/blog/?p=61
date: 2011-05-16 13:58:28.000000000 -04:00
categories:
- Technology
- Windows
tags:
- powershell
- Set-ExecutionPolicy
- scripts
- error
comments: []
---
<blockquote>File NAME.ps1 cannot be loaded because the execution of scripts is disabled on this system. Please see “get-help about_signing” for more details.</blockquote>
You will get this error when the default execution policy is enable, which is <strong>Restricted</strong>: Does not load configuration files or run scripts.

There are six different values that can be set with the "Set-ExecutionPolicy" command;
<ul>
	<li><strong>Restricted</strong>: Does not load configuration files or run scripts. "Restricted" is the default execution policy.</li>
	<li><strong>AllSigned</strong>: Requires that all scripts and configuration  files be signed by a trusted publisher, including scripts that you write  on the local computer.</li>
	<li><strong>RemoteSigned</strong>: Requires that all scripts and  configuration files downloaded from the Internet be signed by a trusted  publisher.</li>
	<li><strong>Unrestricted</strong>: Loads all configuration files and runs all  scripts. If you run an unsigned script that was downloaded from the  Internet, you are prompted for permission before it runs.</li>
	<li><strong>Bypass</strong>: Nothing is blocked and there are no warnings or prompts.</li>
	<li><strong>Undefined</strong>: Removes the currently assigned execution  policy from the current scope. This parameter will not remove an  execution policy that is set in a Group Policy scope.</li>
</ul>
Example of command:

Set-ExecutionPolicy Unrestricted

&nbsp;

Source: <a href="http://technet.microsoft.com/en-us/library/dd347628.aspx">http://technet.microsoft.com/en-us/library/dd347628.aspx</a>
