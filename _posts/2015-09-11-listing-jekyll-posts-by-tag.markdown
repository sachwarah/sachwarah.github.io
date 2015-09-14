---
layout: post
title:  "Listing jekyll posts by tag"
date:   2015-09-11 07:00:00
tags: jekyll how-to
---
I'm used to using WordPress and have used tags and categories to create pages and custom templates. I thought a good exercise to help me understand jekyll is to create a page that lists all the tags used across the site and then display all the posts within that category.

I found a very helpful post on [Joe Kampschmidt's Code](http://www.jokecamp.com/blog/listing-jekyll-posts-by-tag/) and implemented that into the "[Tags](/tags)" page of this blog that you can see on the menu bar.

<!--more-->

The code that does all of the work is below.

{% raw %}
```liquid
{% for tag in site.tags %}
  {% assign t = tag | first %}
  {% assign posts = tag | last %}

  {{ t | downcase }}
<ul>
{% for post in posts %}
  {% if post.tags contains t %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <span class="date">{{ post.date | date: "%B %-d, %Y"  }}</span>
  </li>
  {% endif %}
{% endfor %}
</ul>
{% endfor %}
```
{% endraw %}


So now I need to understand all the liquid template syntax.