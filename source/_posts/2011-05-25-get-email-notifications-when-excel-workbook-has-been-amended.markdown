---
layout: post
status: publish
published: true
title: Get Email notifications when Excel workbook has been amended.
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 151
wordpress_url: http://d87studios.com/blog/?p=151
date: 2011-05-25 14:23:02.000000000 -04:00
categories:
- Technology
- Windows
- Editors' Picks
tags:
- excel
- email notification
- amended
- updated
- macro
- visual basic
- office
comments:
- id: 1327
  author: Kam
  author_email: reddy_kam@yahoo.ca
  author_url: ''
  date: !binary |-
    MjAxMy0wMS0wOCAwMDoyMjowMCAtMDUwMA==
  date_gmt: !binary |-
    MjAxMy0wMS0wOCAwMDoyMjowMCAtMDUwMA==
  content: ! 'Hello.  I tried with Excel 2007 - I do not get anything when I save
    the file.  Should I be getting a message?.


    Thanks


    Kam'
- id: 1328
  author: d87tech
  author_email: david.yurkiewicz@gmail.com
  author_url: ''
  date: !binary |-
    MjAxMy0wMS0wOCAxMzo0MjowMCAtMDUwMA==
  date_gmt: !binary |-
    MjAxMy0wMS0wOCAxMzo0MjowMCAtMDUwMA==
  content: Do you have Outlook setup property? This only works with a local copy of
    outlook.
- id: 1329
  author: Kam
  author_email: reddy_kam@yahoo.ca
  author_url: ''
  date: !binary |-
    MjAxMy0wMS0wOCAxNzoxMzowMCAtMDUwMA==
  date_gmt: !binary |-
    MjAxMy0wMS0wOCAxNzoxMzowMCAtMDUwMA==
  content: ! "We have Outlook Exchange server - and I have a local outlook.  \n\nAny
    suggestions"
- id: 1330
  author: d87tech
  author_email: david.yurkiewicz@gmail.com
  author_url: ''
  date: !binary |-
    MjAxMy0wMS0xMSAxNjoyOTowMCAtMDUwMA==
  date_gmt: !binary |-
    MjAxMy0wMS0xMSAxNjoyOTowMCAtMDUwMA==
  content: ! 'If you have a local (working) copy of Outlook, then the above script
    should work. The only thing that comes to mind, is the macro settings. Make sure
    they are set correctly. '
- id: 1331
  author: URL
  author_email: ''
  author_url: http://www.sZJuFb.net
  date: !binary |-
    MjAxMy0wMS0xOSAxOTo0NDowNiAtMDUwMA==
  date_gmt: !binary |-
    MjAxMy0wMS0xOSAxOTo0NDowNiAtMDUwMA==
  content: ! '<strong>... [Trackback]...</strong>


    [...] Read More: d87studios.com/blog/2011/05/get-email-notifications-when-excel-workbook-has-been-amended/
    [...]...'
- id: 1408
  author: cheap longchamp
  author_email: ''
  author_url: http://www.monroepest.com/LongchampOutletOnline.html
  date: !binary |-
    MjAxMy0wNS0xOCAwODoxMDo0MCAtMDQwMA==
  date_gmt: !binary |-
    MjAxMy0wNS0xOCAwODoxMDo0MCAtMDQwMA==
  content: ! '<strong>cheap longchamp...</strong>


    Aw, this was a very nice post. In thought I wish to put in writing like this moreover
    ?taking time and precise effort to make a very good article?but what can I say?I
    procrastinate alot and under no circumstances appear to get one thing done....'
- id: 1429
  author: Free Download Rivals at War Cheats hack
  author_email: ''
  author_url: http://aggrocheats.com/?p=1092
  date: !binary |-
    MjAxMy0wNy0yMSAxODowMzoyMCAtMDQwMA==
  date_gmt: !binary |-
    MjAxMy0wNy0yMSAxODowMzoyMCAtMDQwMA==
  content: ! '<strong>Free Download Rivals at War Cheats hack...</strong>


    I''m really inspired with your writing talents and also with the format to your
    blog. Is this a paid subject or did you modify it your self? Anyway keep up the
    nice high quality writing, it is uncommon to see a nice blog like this one today.....'
- id: 1430
  author: Bullet Time HD hack
  author_email: ''
  author_url: http://aggrocheats.com/?p=2561
  date: !binary |-
    MjAxMy0wNy0yNCAxMzowNzo0OSAtMDQwMA==
  date_gmt: !binary |-
    MjAxMy0wNy0yNCAxMzowNzo0OSAtMDQwMA==
  content: ! '<strong>Bullet Time HD hack...</strong>


    After I originally commented I seem to have clicked on the -Notify me when new
    comments are added- checkbox and now whenever a comment is added I recieve four
    emails with the exact same comment. There has to be a means you can remove me
    from that servi...'
- id: 1431
  author: Karol
  author_email: karito114@hotmail.com
  author_url: ''
  date: !binary |-
    MjAxMy0wOC0wNSAxNjo1MzowMCAtMDQwMA==
  date_gmt: !binary |-
    MjAxMy0wOC0wNSAxNjo1MzowMCAtMDQwMA==
  content: Hello, What if you have Windows Live Mail, would this script work?
---
Recently I ran across a situation where i had an Excel workbook that was on a shared drive, this file would get updated by different employees on any given time of the day. I need it a way to alert someone in management every time this file was amended. This was my solution:
<pre>Private Sub Workbook_BeforeSave(ByVal SaveAsUI As Boolean, Cancel As Boolean)
    Dim OutApp As Object
    Dim OutMail As Object
    Const SendTo As String = "<span style="color: #3366ff;">davidy@Initech.com</span>"

    Set OutApp = CreateObject("Outlook.Application")

    OutApp.Session.Logon
    Set OutMail = OutApp.CreateItem(0)

    With OutMail
        .To = SendTo
        .Subject = ThisWorkbook.Name &amp; " has been amended"
        .Body = " <span style="color: #3366ff;">The Workbook has been updated</span>!"
        .Send
    End With

    Set OutMail = Nothing
    Set OutApp = Nothing
End Sub</pre>
This Visual basic code sends an email via Outlook every time the workbook has been updated. For this code to fully work you will need to edit your macro settings in Excel.
<h2>Edit Macro Security Settings:</h2>
<strong>Office 2003</strong> - Tools &gt; Macro &gt; Security.
<strong>Office 2007</strong> - Click the Microsoft Office Button , and then click Excel Options. In the Trust Center category, click Trust Center Settings, and then click the Macro Settings category.

[caption id="attachment_155" align="aligncenter" width="300" caption="Macro Security in Excel 2003"]<a href="http://d87studios.com/blog/wp-content/uploads/2011/05/macro_security.png"><img class="size-medium wp-image-155" title="macro_security_2003" src="http://d87studios.com/blog/wp-content/uploads/2011/05/macro_security-300x292.png" alt="Macro Security in Excel 2003" width="300" height="292" /></a>[/caption]

To make this VB code work correctly, you will need to set your Macro Security level to Medium or lower.
<h2>Inserting the Code:</h2>
Simply right click on the worksheet tab and click View Code. This will open the Microsoft Visual Basic screen.

[caption id="attachment_157" align="aligncenter" width="300" caption="Click View Code to open the Microsoft Visual Basic screen"]<a href="http://d87studios.com/blog/wp-content/uploads/2011/05/excel_viewcode.png"><img class="size-medium wp-image-157" title="excel_viewcode_2003" src="http://d87studios.com/blog/wp-content/uploads/2011/05/excel_viewcode-300x231.png" alt="Click View Code to open the Microsoft Visual Basic screen" width="300" height="231" /></a>[/caption]

Once you have the Microsoft VB screen open you can paste the code and begin editing it.
<p style="text-align: center;">&nbsp;</p>


[caption id="attachment_159" align="aligncenter" width="620" caption="A view of the Microsoft Visual Basic screen"]<a href="http://d87studios.com/blog/wp-content/uploads/2011/05/workbook_code.png"><img class="size-large wp-image-159" title="workbook_code" src="http://d87studios.com/blog/wp-content/uploads/2011/05/workbook_code-1024x571.png" alt="A view of the Microsoft Visual Basic screen" width="620" height="345" /></a>[/caption]
<p style="text-align: left;">&nbsp;</p>
<p style="text-align: left;">Don't forget to add your email address and if you would like to, you can customized the message that would be display on the body of the email. Just look at the highlighted parts on the picture above.</p>
<p style="text-align: left;"><em>If you have any questions feel free to leave a comment below.</em></p>
<p style="text-align: center;">&nbsp;</p>
