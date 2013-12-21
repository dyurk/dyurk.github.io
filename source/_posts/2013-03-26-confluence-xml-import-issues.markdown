---
layout: post
status: publish
published: true
title: Confluence XML Import Issues
author: David Yurkiewicz
author_login: admin
author_email: david.yurkiewicz@gmail.com
wordpress_id: 682
wordpress_url: http://d87studios.com/blog/?p=682
date: 2013-03-26 13:35:01.000000000 -04:00
categories:
- Technology
- Linux
- web operations
tags:
- confluence
- wiki
- xml
- import
comments: []
---
Find the class that the import is having issues with. For this example ContentPermission is the problem.

<pre class="prettyprint">Error while importing backup: not-null property references a null or transient value: com.atlassian.confluence.security.ContentPermission.owningSet
Caused by: net.sf.hibernate.PropertyValueException: not-null property references a null or transient value: com.atlassian.confluence.security.ContentPermission.owningSet</pre>

Delete all ContentPermission entries from the XML file - this will remove all unnecessary/unsupported classes and will allow the import to continue. Open the zip file and edit entities.xml
<br>

Search for `<object class="ContentPermission"...>` You will see `<object>` entries like this:


```xml
<object class="ContentPermission" package="com.atlassian.confluence.security">
<id name="id">17072133</id>
<property name="type"><![CDATA[View]]></property>
<property name="userName"><![CDATA[corporatetrainer]]></property>
<property name="groupName"/><property name="owningSet" class="ContentPermissionSet" package="com.atlassian.confluence.security"><id name="id">17039363</id>
</property>
<property name="creatorName"><![CDATA[corporatetrainer]]></property>
<property name="creationDate">2011-05-19 10:22:05.000</property>
<property name="lastModifierName"><![CDATA[corporatetrainer]]></property>
<property name="lastModificationDate">2011-05-19 10:22:05.000</property>
</object>
```


Helpful on-liner to remove the entries from entities.xml

```bash
$ sed -i '/<object class="ContentPermission"/,/<\/object>/d' entities.xml
```

Make sure there are no syntax errors that will cause the import to fail
<pre>xmllint --noout entities.xml</pre>

Retry the import and Good Luck!
