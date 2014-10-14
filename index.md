---
layout: page
title: Er's Blog
tagline: 测试 
---
{% include JB/setup %}

<ul class="posts">
  {% for post in site.posts %}
    <li><span><h4>{{ post.date | date_to_string }}</h4></span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
