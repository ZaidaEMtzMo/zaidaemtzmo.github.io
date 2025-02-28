---
layout: default
title: "Home"
permalink: /fr/
lang: fr
---

# Bienvenue sur mon site Web !

This is my personal space where I share my thoughts, interests, and research.

## Derniers Articles
{% assign filtered_posts = site.posts | where: "lang", page.lang | sort: "date" | reverse %}
{% for post in filtered_posts limit:5 %}
  - [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%d %B %Y" }}
{% endfor %}