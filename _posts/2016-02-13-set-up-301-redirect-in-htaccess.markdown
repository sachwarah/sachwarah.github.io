---
layout: post
title:  "How to setup a redirect in .htaccess after you have moved a website"
date:   2016-02-13 12:00:00
tags: wordpress how-to
---

After you have moved a website to a new domain the code below can be inserted into the old domain's
.htaccess file to setup a redirect.

This code was found at [creare.co.uk](https://www.creare.co.uk/blog/seo-advice/how-to-301-to-a-new-domain)

```
RewriteEngine on
RewriteCond %{HTTP_HOST} !^www\.newdomain\.co.uk 
RewriteRule (.*) http://www.newdomain.co.uk/$1 [R=301,L]
```