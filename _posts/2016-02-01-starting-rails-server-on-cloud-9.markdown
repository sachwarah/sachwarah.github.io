---
layout: post
title:  "Starting rails server on Cloud9"
date:   2016-02-01 11:40:00
tags: ruby rails how-to cloud9
---

The [Running a rails app](https://docs.c9.io/docs/jekyll) page on Cloud9 says that the correct way of starting `rails server` on Cloud9 is:

```
rails s -b $IP -p $PORT
```

You can add an alias to the command line by typing `c9 ~/.bash_alaises` to open the alias file. 
Then insert the following line.

````
alias rs='rails server -b $IP -p $PORT'
````
Open a new terminal window, move to your app's directory and rs will now start 
the rails server!





