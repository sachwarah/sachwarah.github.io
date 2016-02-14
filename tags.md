---
layout: page
title: Tags
permalink: /tags/
---
{% assign ordered_tags = site.tags | sort %}
<ul>
{% for tag in ordered_tags %}
  {% assign t = tag | first %}
  <li><a href="#{{ t | downcase }}">{{ t | downcase }}</a></li>
{% endfor %}
</ul>
  

{% for tag in ordered_tags %}
  {% assign t = tag | first %}
  {% assign posts = tag | last %}

<div id="{{ t | downcase }}">{{ t | downcase }}</div>
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