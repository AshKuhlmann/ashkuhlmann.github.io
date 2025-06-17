---
layout: default               # built-in layout
title: "Welcome"
nav_order: 1                  # first in navbar
description: "Recent posts and intro."
permalink: /
---

# 👋 Hi there, I’m Ash

_Aspiring Junior SysAdmin documenting projects, certifications, and lessons learned on the way to my first IT role._

## Recent posts
{% for post in site.posts limit:5 %}
- [{{ post.title }}]({{ post.url | relative_url }}) <small>{{ post.date | date: "%b %d %Y" }}</small>
{% endfor %}

