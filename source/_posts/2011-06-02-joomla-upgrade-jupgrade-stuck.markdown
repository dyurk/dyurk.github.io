---
layout: post
status: publish
published: true
title: Joomla Upgrade. jUpgrade Stuck
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 187
wordpress_url: http://d87studios.com/blog/?p=187
date: 2011-06-02 14:42:14.000000000 -04:00
categories:
- Technology
tags:
- error
- joomla
- jupgrade
comments: []
---
<p style="text-align: left;">When upgrading from Joomla 1.5.X to 1.6 i ran through an issue with jUpgrade. It seem like it was always getting stuck in the Downloading process. After restarting the process different times with different variables, i still could not get past the Downloading step. So i figure i check the Parameters settings, there i was able to disable the Download process. After changing the setting i restarted the upgrade process and it work correctly.</p>

<div class="mceTemp" style="text-align: left;"><dl id="attachment_189" class="wp-caption alignleft" style="width: 493px;"> <dt class="wp-caption-dt"><a href="http://d87studios.com/blog/wp-content/uploads/2011/06/joomla_upgrade.png"><img class="size-full wp-image-189" title="joomla_upgrade_stuck" src="http://d87studios.com/blog/wp-content/uploads/2011/06/joomla_upgrade.png" alt="jUpgrade is stuck in Downloading" width="483" height="252" /></a></dt> <dd class="wp-caption-dd">jUpgrade is stuck in Downloading </dd> </dl></div>
<br>
<p class="wp-caption" style="text-align: left;"><em>Please Note: Before we start, make sure you have the <strong>System - Mootools Upgrade </strong>module enable. This is usually the main reason many upgrades have failed.</em></p>
<p style="text-align: left;">If your Mootools Upgrade module is enable and jUpgrade keeps getting stuck, then try the following:</p>
<p style="text-align: left;">Go to your Components and click on jUpgrade. Click on the Parameters button. Looks like this: <img class="size-full wp-image-190 alignnone" style="border: 1px solid black;" title="joomla_parameters" src="http://d87studios.com/blog/wp-content/uploads/2011/06/joomla_parameters.png" alt="" width="63" height="48" /></p>
<p style="text-align: left;">Disable the Downloading step by selecting <em>YES </em>in the <strong>Skip Download </strong>setting.</p>

<div class="mceTemp" style="text-align: left;"><dl id="attachment_191" class="wp-caption alignnone" style="width: 573px;"> <dt class="wp-caption-dt"><a href="http://d87studios.com/blog/wp-content/uploads/2011/06/joomla_jupgrade_settings.png"><img class="size-full wp-image-191 " title="joomla_jupgrade_settings" src="http://d87studios.com/blog/wp-content/uploads/2011/06/joomla_jupgrade_settings.png" alt="jUpgrade Skip Download" width="563" height="228" /></a></dt> <dd class="wp-caption-dd">jUpgrade Skip Download</dd> </dl></div>
<p style="text-align: left;">&nbsp;</p>
<p style="text-align: left;">Now retry the upgrade and at the end you should see this screen:</p>

<div class="mceTemp" style="text-align: left;"><dl id="attachment_192" class="wp-caption alignnone" style="width: 480px;"> <dt class="wp-caption-dt"><a href="http://d87studios.com/blog/wp-content/uploads/2011/06/joomla_upgrade_done.png"><img class="size-full wp-image-192 " title="joomla_upgrade_done" src="http://d87studios.com/blog/wp-content/uploads/2011/06/joomla_upgrade_done.png" alt="Joomla Upgrade Done!" width="470" height="122" /></a></dt> <dd class="wp-caption-dd">Joomla Upgrade Done!</dd> </dl></div>
<p style="text-align: left;">&nbsp;</p>
<p style="text-align: left;">If you still can't get pass the download step, you might new to download the upgrade file yourself and upload it in the temp folder located in your Joomla directory.</p>
