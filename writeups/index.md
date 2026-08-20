---
title: "Writeups"
nav_order: 6
has_children: true
permalink: /writeups/index.html
description: "CTF solves, vulnerability writeups, CVEs, and research notes."
---

# Writeups

The employer-facing proof: CTF solves, vulnerability writeups, disclosed CVEs, and research notes.
This is where "I studied X" turns into "here's me doing X."

<!-- HOW TO ADD A WRITEUP:
     1. Copy writeups/_TEMPLATE.md to a new file, e.g. writeups/ssrf-in-acme-app.md
     2. Fill in the front matter (title, parent: Writeups, date) and the sections.
     3. It appears below automatically, newest first.
     Keep responsible-disclosure rules in mind — only publish what you're
     authorized to, and redact where you must. -->

## All writeups

{% assign posts = site.html_pages | where: "parent", "Writeups" | sort: "date" | reverse %}
{% for w in posts %}
- [{{ w.title }}]({{ w.url | relative_url }}) <small>{% if w.date %}{{ w.date | date: "%b %d, %Y" }}{% endif %}</small>
{% endfor %}
