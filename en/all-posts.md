---
layout: default
title: "All Posts"
permalink: /en/all-posts/
lang: en
---
# All Posts

{% assign filtered_posts = site.posts | where: "lang", page.lang | sort: "date" | reverse %}
{% for post in filtered_posts %}
  - [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
