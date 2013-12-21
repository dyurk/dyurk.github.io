---
layout: post
status: publish
published: true
title: Bash Shell Exit Status
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 503
wordpress_url: http://d87studios.com/blog/?p=503
date: 2012-06-19 00:57:41.000000000 -04:00
categories:
- Technology
- Linux
tags:
- bash
- shell
- exit codes
comments: []
---
Exit status codes are helpful when creating shell scripts with IF statements. They are also helpful when you are trying to troubleshoot the outcome of a command. You can use "<em>echo</em> <em>$?"</em> to find out the exit status. In the terminal exit codes are not displayed on the screen by default, we have to echo them. Here are a few examples:
<pre lang="shell" prompt="$"> grep "asda" test.log
</pre>
In this case we get no output. Now if we echo $? we should get an exit code:
<pre lang="shell" prompt="$">$ grep "asda" test.log
<br>$ echo $?
  1</pre>
In this case we get a "1"  which is a failure. "0" = Success, "2" = Incorrect Usage, "126" = Not Executable, "127" = Command Not Found.
