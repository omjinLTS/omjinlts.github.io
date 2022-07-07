---
title: "개발을 해봅시다"
permalink: /dev/
layout: archive
author_profile: true
taxonomy: Dev
---

{% assign posts = site.categories.dev %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
