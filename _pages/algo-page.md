---
title: "알고리즘 정리"
permalink: /algo/
layout: archive
author_profile: true
toxonomy: algorithm
---

{% assign posts = site.categories.algorithm %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}