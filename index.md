---
layout: default               # built-in layout
title: "Welcome"
nav_order: 1                  # first in navbar
description: "Recent posts and intro."
permalink: /
---

# 👋 Hi there, I’m Ash

_Aspiring Junior SysAdmin documenting projects, certifications, and lessons learned on the way to my first IT role._

<p align="center">
  <img src="{{ '/assets/images/frontpage.png' | relative_url }}" alt="Front page image">
</p>

## Systems speak in logs. This is mine.

Here you'll find projects in Linux, networking, automation, and scripting—each reflecting practical skills I've built with intention and rigor.

Take a look at my recent posts below!

## Recent posts
{% for post in site.posts limit:5 %}
- [{{ post.title }}]({{ post.url | relative_url }}) <small>{{ post.date | date: "%b %d %Y" }}</small>
{% endfor %}

