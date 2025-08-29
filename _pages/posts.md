---
layout: archive
title: "Posts"
permalink: /posts/
classes: wide
author_profile: false
entries_layout: list   # or "grid"
show_excerpts: true    # show first paragraph under each post
---

{% for post in site.posts %}
  {% include archive-single.html %}
{% endfor %}
