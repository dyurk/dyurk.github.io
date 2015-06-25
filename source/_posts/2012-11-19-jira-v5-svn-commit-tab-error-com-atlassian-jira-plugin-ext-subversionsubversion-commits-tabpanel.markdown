---
layout: post
status: publish
published: true
title: JIRA v5 SVN commit tab error
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 574
wordpress_url: http://d87studios.com/blog/?p=574
date: 2012-11-19 18:09:49.000000000 -05:00
categories:
- Technology
- Linux
- Subversion
tags:
- error
- svn
- JIRA
- subversion
comments: []
---
<pre>JIRA v5 SVN commit tab error. com.atlassian.jira.plugin.ext.subversion:subversion-commits-tabpanel</pre>


To fix this issue you will need to remove the <strong>atlassian-subversion-revisions </strong>folder which is located under the home directory of the JIRA user.
<pre>$JIRA_HOME/caches/indexes/plugins/atlassian-subversion-revisions/</pre>
Now restart JIRA, the subversion tab should now start displaying commits.

&nbsp;
<h6>source: <a href="https://confluence.atlassian.com/display/JIRAKB/How+to+resolve+JIRA+Sub+Version+Plugin+Errors+after+an+upgrade">https://confluence.atlassian.com/display/JIRAKB/How+to+resolve+JIRA+Sub+Version+Plugin+Errors+after+an+upgrade</a></h6>
