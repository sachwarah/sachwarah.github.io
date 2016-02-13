---
layout: post
title:  "How to setup a redirect in .htaccess after ou have moved a website"
date:   2016-02-13 12:00:00
tags: wordpress how-to
---


```
RewriteEngine on
RewriteCond %{HTTP_HOST} !^www\.newdomain\.co.uk 
RewriteRule (.*) http://www.newdomain.co.uk/$1 [R=301,L]
```