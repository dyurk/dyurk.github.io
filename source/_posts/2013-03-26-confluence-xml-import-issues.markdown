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
Caused by: net.sf.hibernate.PropertyValueException: not-null property references a null or transient value: com.atlassian.confluence.security.ContentPermission.owningSet
</pre>
Delete all ContentPermission entries from the XML file - this will remove all unnecessary/unsupported classes and will allow the import to continue. Open the zip file and edit entities.xml
<br>
Search for <code><object class="ContentPermission"...>.</code> You will see <code><object></code> entries like this:

<pre class="prettyprint">

237081 <object class="ContentPermission" package="com.atlassian.confluence.security">
237082 <id name="id">17072133</id>
237083 <property name="type"><![CDATA[View]]></property>
237084 <property name="userName"><![CDATA[corporatetrainer]]></property>
237085 <property name="groupName"/><property name="owningSet" class="ContentPermissionSet" package="com.atlassian.confluence.security"><id name="id">17039363</id>
237086 </property>
237087 <property name="creatorName"><![CDATA[corporatetrainer]]></property>
237088 <property name="creationDate">2011-05-19 10:22:05.000</property>
237089 <property name="lastModifierName"><![CDATA[corporatetrainer]]></property>
237090 <property name="lastModificationDate">2011-05-19 10:22:05.000</property>
237091 </object>

</pre>

Helpful on-liner to remove the entries from entities.xml

<pre><code>sed -i '/<object class="ContentPermission"/,/<\/object>/d' entities.xml</code></pre>

Make sure there are no syntax errors that will cause the import to fail
<pre><code>xmllint --noout entities.xml</code></pre>

Retry the import and Good Luck!
