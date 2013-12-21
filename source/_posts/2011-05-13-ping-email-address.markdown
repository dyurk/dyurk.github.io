---
layout: post
status: publish
published: true
title: ! '"PING" Email Address'
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 19
wordpress_url: http://d87studios.com/blog/?p=19
date: 2011-05-13 16:40:21.000000000 -04:00
categories:
- Technology
tags:
- network
- email
comments: []
---
Open CMD

For this example lets try GMAIL
<pre>nslookup –type=mx gmail.com

</pre>
You will get something like this:
<pre>gmail.com MX preference=30, exchanger = alt3.gmail-smtp-in.l.google.com
gmail.com MX preference=20, exchanger = alt2.gmail-smtp-in.l.google.com
gmail.com MX preference=5,  exchanger = gmail-smtp-in.l.google.com
gmail.com MX preference=10, exchanger = alt1.gmail-smtp-in.l.google.com
gmail.com MX preference=40, exchanger = alt4.gmail-smtp-in.l.google.com
</pre>
Now lets connect to the mail server
<pre>telnet gmail-smtp-in.l.google.com 25</pre>
&nbsp;

Get acknowledge by saying Hello
<pre>HELO</pre>
Type your email address
<pre>mail from:&lt;joe@doe.com&gt;</pre>
Type the email address you want to test
<pre>rcpt to:&lt;testemail@gmail.com&gt;



</pre>
You can also use this website:

http://verify-email.org/

&nbsp;

<em>Source: http://www.labnol.org/software/verify-email-address/18220/</em>
