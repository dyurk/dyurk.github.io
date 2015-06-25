---
layout: post
status: publish
published: true
title: Get Email notifications when Excel workbook has been amended.
author: DYURK
author_login: admin
author_email: null@dev.com
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
---
Recently I ran across a situation where i had an Excel workbook that was on a shared drive, this file would get updated by different employees on any given time of the day. I need it a way to alert someone in management every time this file was amended. This was my solution:

```vbnet
Private Sub Workbook_BeforeSave(ByVal SaveAsUI As Boolean, Cancel As Boolean)
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
End Sub
```
This Visual basic code sends an email via Outlook every time the workbook has been updated. For this code to fully work you will need to edit your macro settings in Excel.
<h2>Edit Macro Security Settings:</h2>
<strong>Office 2003</strong> - Tools &gt; Macro &gt; Security.
<strong>Office 2007</strong> - Click the Microsoft Office Button , and then click Excel Options. In the Trust Center category, click Trust Center Settings, and then click the Macro Settings category.

<a href="http://d87studios.com/blog/wp-content/uploads/2011/05/macro_security.png"><img class="size-medium wp-image-155" title="macro_security_2003" src="http://d87studios.com/blog/wp-content/uploads/2011/05/macro_security-300x292.png" alt="Macro Security in Excel 2003" width="300" height="292" /></a>

To make this VB code work correctly, you will need to set your Macro Security level to Medium or lower.
<h2>Inserting the Code:</h2>
Simply right click on the worksheet tab and click View Code. This will open the Microsoft Visual Basic screen.

<a href="http://d87studios.com/blog/wp-content/uploads/2011/05/excel_viewcode.png"><img class="size-medium wp-image-157" title="excel_viewcode_2003" src="http://d87studios.com/blog/wp-content/uploads/2011/05/excel_viewcode-300x231.png" alt="Click View Code to open the Microsoft Visual Basic screen" width="300" height="231" /></a>

Once you have the Microsoft VB screen open you can paste the code and begin editing it.
<p style="text-align: center;">&nbsp;</p>


<a href="http://d87studios.com/blog/wp-content/uploads/2011/05/workbook_code.png"><img class="size-large wp-image-159" title="workbook_code" src="http://d87studios.com/blog/wp-content/uploads/2011/05/workbook_code-1024x571.png" alt="A view of the Microsoft Visual Basic screen" width="620" height="345" /></a>
<p style="text-align: left;">&nbsp;</p>
<p style="text-align: left;">Don't forget to add your email address and if you would like to, you can customized the message that would be display on the body of the email. Just look at the highlighted parts on the picture above.</p>
<p style="text-align: center;">&nbsp;</p>
