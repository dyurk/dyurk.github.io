---
layout: post
status: publish
published: true
title: Can't open attachments in Outlook?
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 25
wordpress_url: http://d87studios.com/blog/?p=25
date: 2011-05-13 16:42:37.000000000 -04:00
categories:
- Technology
- Windows
tags:
- Outlook
comments: []
---
<div>
<div>

If you are getting the following error:
<p class="wp-caption-dd"><strong>"Can't create file: filename.xx. Right-click the folder you   want to create  the file in, and then click Properties on the shortcut   menu to check  your permissions for the folder".</strong></p>
1.  Open REGEDIT.EXE and go to Edit -&gt; Find... In the Find dialog box  type "<strong>OutlookSecureTempFolder</strong>" without the quotes and locate that  registry key.2. That key will contain the actual folder location, and will look like:

C:Documents and Settings%USER_NAME%Local SettingsTemporary Internet FilesOLK# (where # is a random letter or number)

3. Copy the location of that folder.

4. Click on Start -&gt; Run... and paste the folder location from step #4 then click OK.

5. Windows Explorer will open that folder. Please, delete all files present.

6. Restart Microsoft Outlook and you should be able to open your attachments.

</div>
</div>
