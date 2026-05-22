---
layout: page
title: Blog
permalink: /blog/
---

## Blog

{% if site.posts.size == 0 %}
No posts yet — check back tomorrow.
{% else %}
<ul>
{% for post in site.posts %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span style="color:#888; font-size:0.9em;">— {{ post.date | date: "%b %-d, %Y" }}</span>
  </li>
{% endfor %}
</ul>
{% endif %}
