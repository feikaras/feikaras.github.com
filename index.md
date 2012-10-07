---
layout: page
title: Hello World!
tagline: Supporting tagline
---
{% include JB/setup %}
中文的测试

- a
- b
- c
- 中文
- d
- e

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>


