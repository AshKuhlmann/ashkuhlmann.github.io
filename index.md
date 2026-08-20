---
layout: default
title: "Home"
nav_order: 1
description: "Ash Kuhlmann — offensive security portfolio, roadmap, and learning log."
permalink: /
---

# Ash Kuhlmann

<!-- FILL IN: one-line positioning statement. Keep it short and specific.
     Example: "Aspiring offensive security engineer with a CS background —
     working toward web/API appsec today, vulnerability research long-term." -->
_Aspiring offensive security engineer with a CS background — building toward web/API application security now and vulnerability research long-term._

<p align="center">
  <img src="{{ '/assets/images/frontpage.png' | relative_url }}" alt="Banner">
</p>

This site is my **living record** of getting into offensive security: the plan I'm following, the certifications and skills I'm building, the projects and writeups that prove it, and the honest week-to-week log of the work. It updates as I do.

---

## 🎯 Currently

<!-- FILL IN: update these three lines whenever your focus shifts. This is the
     single highest-signal block on the site — keep it current. -->

- **Now:** _Phase 1 — systems & C/assembly foundations_
- **Focus this week:** _<!-- e.g. "GDB + stack-overflow lab; PortSwigger SQLi track" -->_
- **Next up:** _<!-- e.g. "Finish PortSwigger auth labs, start the AD lab build" -->_

➡️ **Full progress:** see the [Progress Tracker]({{ '/progress.html' | relative_url }}) · **The plan:** see the [Roadmap]({{ '/roadmap.html' | relative_url }})

---

## 📌 Featured work

<!-- FILL IN: hand-pick 2-3 things you're proudest of and link them here.
     This is what a busy employer looks at first. Leave it empty until you
     have something real — an empty section beats filler. -->

- _Add your best project or writeup here once you have one — e.g. a CVE, a CTF writeup, or a tool you built._

Browse everything in [Projects]({{ '/projects/index.html' | relative_url }}) and [Writeups]({{ '/writeups/index.html' | relative_url }}).

---

## 🗒️ Latest from the journal

{% assign entries = site.html_pages | where: "parent", "Journal" | sort: "date" | reverse %}
{% for post in entries limit:5 %}
- [{{ post.title }}]({{ post.url | relative_url }}) <small>{{ post.date | date: "%b %d, %Y" }}</small>
{% endfor %}

Read the full [Journal]({{ '/journal/index.html' | relative_url }}).
