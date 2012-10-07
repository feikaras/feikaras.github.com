---
layout: page
title: RavenWhite
tagline: linux,ubuntu,slackware,php,javascript,html
---
{% include JB/setup %}
Hello,大家好～

- Linux fan
- PHP码农
- 动画fan
- 日语fan

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>


