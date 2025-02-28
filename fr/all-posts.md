---
layout: default
title: "All Posts"
permalink: /fr/all-posts/
lang: fr
---
## Tous les articles

{% assign filtered_posts = site.posts | where: "lang", page.lang | sort: "date" | reverse %}
{% assign post_count = filtered_posts | size %}

{% for post in filtered_posts %}
  {% assign lang = post.lang | default: site.lang %}
  {% assign month_index = post.date | date: "%-m" | minus: 1 %}
  {% assign month_translated = site.months[lang][month_index] %}

  - [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "le %d" }} {{ month_translated }} {{ post.date | date: "%Y" }}
{% endfor %}
