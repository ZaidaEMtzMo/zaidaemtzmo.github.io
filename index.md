---
layout: default
title: Home
---

# Welcome to My Website

This is my personal space where I share my thoughts, interests, and research.

## Latest Posts
{% for post in site.posts limit:5 %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
