---
title: "Journal"
nav_order: 7
has_children: true
permalink: /journal/index.html
description: "Weekly learning log and reflections."
---

# Journal

The honest week-to-week log: what I studied, what clicked, what didn't, and what's next. The
running narrative behind the [Progress Tracker]({{ '/progress.html' | relative_url }}).

<!-- HOW TO ADD AN ENTRY:
     1. Copy journal/_TEMPLATE.md to journal/YYYY-MM-DD.md (use the real date).
     2. Fill in the front matter (title, parent: Journal, date) and write.
     3. It appears below and on the home page automatically, newest first. -->

## Entries

{% assign entries = site.html_pages | where: "parent", "Journal" | sort: "date" | reverse %}
{% for post in entries %}
- [{{ post.title }}]({{ post.url | relative_url }}) <small>{% if post.date %}{{ post.date | date: "%b %d, %Y" }}{% endif %}</small>
{% endfor %}
