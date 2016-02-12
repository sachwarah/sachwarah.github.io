---
layout: post
title:  "Update a Wordpress Database after changing hosts"
date:   2016-02-01 11:40:00
tags: wordpress mysql how-to
---

If found a great set of mysql update commands written on [wpbeaches](https://wpbeaches.com/updating-wordpress-mysql-database-after-moving-to-a-new-url/).

Once the database has been transferred to the new host, log in to the database
administration panel and run the following in an "SQL" tab.

```
UPDATE wp_options SET option_value = replace(option_value, 'http://www.oldurl', 'http://www.newurl') WHERE option_name = 'home' OR option_name = 'siteurl';

UPDATE wp_posts SET guid = replace(guid, 'http://www.oldurl','http://www.newurl');

UPDATE wp_posts SET post_content = replace(post_content, 'http://www.oldurl', 'http://www.newurl');

UPDATE wp_postmeta SET meta_value = replace(meta_value,'http://www.oldurl','http://www.newurl');
```

This will update most of the database but may miss a few links that are held within
PHP arrays that have been saved to the database as serialized data.