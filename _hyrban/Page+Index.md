---
layout: hyrban
title: Page Index
date: 2022-06-10
description: An index of pages
---
This is a list of all pages in this site.
<ul>
{% assign contents = site.hyrban %}{% for post in contents %}
  <li><a href="{{ post.url }}">{% if post.title == "$(file)" %}{{ post.name }}{% else %}{{ post.title }}{% endif %}</a></li>
{% endfor %}
</ul>
