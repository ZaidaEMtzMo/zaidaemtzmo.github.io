---
layout: default
title: "All Posts"
permalink: /es/all-posts/
lang: es
---
# Todas las entradas

{% assign filtered_posts = site.posts | where: "lang", page.lang | sort: "date" | reverse %}
{% for post in filtered_posts %}
  - [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
