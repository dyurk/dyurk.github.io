---
layout: post
status: publish
published: true
title: Confluence backup errors
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 633
wordpress_url: http://d87studios.com/blog/?p=633
date: 2013-02-20 15:17:32.000000000 -05:00
categories:
- Technology
- Linux
- web operations
tags:
- confluence
- wiki
comments: []
---
<pre>The following error(s) occurred:
com.atlassian.confluence.importexport.ImportExportException: Couldn't backup database data. at com.atlassian.confluence.importexport.impl.AbstractXmlExporter.backupEntities(AbstractXmlExporter.java:197) at com.atlassian.confluence.importexport.impl.AbstractXmlExporter.backupEverything(AbstractXmlExporter.java:99) at com.atlassian.confluence.importexport.impl.FileXmlExporter.backupEverything(FileXmlExporter.java:76)</pre>
Java is running out of memory.

To increase heap or perm gen space memory in Linux installations,

Edit $CONFLUENCE_HOME/bin/setenv.sh

Find the section JAVA_OPTS="-Xms256m -Xmx512m -XX:MaxPermSize=256m and set accordingly.  Xmx is maximum, Xms is minimum, and MaxPermSize is PermGen.
