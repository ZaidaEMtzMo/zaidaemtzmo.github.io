---
layout: default
title: "All Posts"
permalink: /fr/all-posts/
lang: fr
---
# Tous les articles

{% assign filtered_posts = site.posts | where: "lang", page.lang | sort: "date" | reverse %}
{% for post in filtered_posts %}
  - [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
