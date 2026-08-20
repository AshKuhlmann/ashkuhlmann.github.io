---
title: "Projects"
nav_order: 5
has_children: true
permalink: /projects/index.html
description: "Hands-on builds, labs, and tools."
---

# Projects

Hands-on builds, labs, and tools — the things I made, not just challenges I solved. Each one is
evidence for a skill on the [Progress Tracker]({{ '/progress.html' | relative_url }}).

<!-- HOW TO ADD A PROJECT:
     1. Copy projects/_TEMPLATE.md to a new file, e.g. projects/afl-fuzzing-harness.md
        (or a folder projects/my-project/my-project.md for multi-page projects).
     2. Fill in the front matter (title, parent: Projects, nav_order) and the sections.
     3. It appears in the list below automatically.
     Files starting with "_" (like _TEMPLATE.md) are ignored by Jekyll and never publish. -->

## All projects

{% assign projs = site.html_pages | where: "parent", "Projects" | sort: "nav_order" %}
{% for p in projs %}
- [{{ p.title }}]({{ p.url | relative_url }})
{% endfor %}
