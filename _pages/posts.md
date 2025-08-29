---
layout: archive
title: "Posts"
permalink: /posts/
classes: wide
author_profile: true
entries_layout: list   # or "grid"
show_excerpts: true    # show first paragraph under each post
---

Here I share some useful research notes and news, as well as some of my collections of the photographs of nature, birds, and blue/night-sky.

{% for post in site.posts %}
  {% include archive-single.html %}
{% endfor %}
