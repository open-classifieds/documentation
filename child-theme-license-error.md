---
title:  Troubleshooting license error of child theme activation
date:   2016-06-29 11:27:04
categories: Themes
tags: Themes, Technical, SelfHosted
permalink: /troubleshoot-child-theme/
keywords: license, error, theme, panel, activate, appearance
---
<div class="alert alert-warning">
<strong><i class="glyphicon glyphicon-warning-sign"></i> </strong> This guide is only for Yclas Self Hosted!
</div>

One common error that users face is related to the license of their child theme. If you are trying to activate your child theme but you are getting an error indicating that your license number is already in use, then you need to **follow the instructions below**:

1. **Backup** your website **files and database**.
2. Login into your hosting **cPanel**, go to your **Database**, table oc2\_config, **find and delete** the entry with "group_name" = "theme" and "config_key" = "_your premium theme name_", if exists.
3. **Find** the entry with config_key = _theme_ and **change** config_value to _default_.
4. Go into your **cPanel File Manager** and delete everything inside oc/cache/
5. Login into your admin panel and activate your theme! ;)

<br>

If you still have any questions and need some help to activate your child theme, please use our [professional support](https://selfhosted.yclas.com/support/)! 

In case you don't have the required technical knowledge to follow this guide, we can fix the error for you by purchasing [One time support](https://selfhosted.yclas.com/services/one-time-support.html).








