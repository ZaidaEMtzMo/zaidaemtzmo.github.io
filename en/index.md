---
layout: default
title: "Home"
permalink: /en/
lang: en
---

# Welcome to My Website !

This is my personal space where I share my thoughts, interests, and research.

## Latest Posts
{% assign filtered_posts = site.posts | where: "lang", page.lang | sort: "date" | reverse %}
{% assign post_count = filtered_posts | size %}

{% for post in filtered_posts limit:5 %}
  {% assign lang = post.lang | default: site.lang %}
  {% assign month_index = post.date | date: "%-m" | minus: 1 %}
  {% assign month_translated = site.months[lang][month_index] %}

  - [{{ post.title }}]({{ post.url }}) - {{ month_translated }} {{ post.date | date: "%d," }} {{ post.date | date: "%Y" }}
{% endfor %}

{% if post_count > 5 %}
  <p><a href="{{ site.nav_links[page.lang].AllPosts | relative_url }}">{{ site.data.translations[page.lang].view_all }}</a></p>
{% endif %}