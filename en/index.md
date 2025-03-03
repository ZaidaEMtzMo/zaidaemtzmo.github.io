---
layout: default
title: "Home"
permalink: /en/
lang: en
---

# Welcome to my website!

My name is Zaida. I was born in Mexico City, Mexico, and from an early age, I was fascinated by the complexity of life. At 12 years old, a teacher asked us to design a life plan, and I eagerly wrote that I would become a marine biologist and pursue a Ph.D. abroad. I followed that vision during my undergraduate studies, majoring in Biology in the [National Autonomous University of Mexico](https://www.fciencias.unam.mx/). Along the way, I discovered neuroscience and fell in love with it, not only for the intricacies of the human brain and how it shapes our behavior, but also for its many applications in health.

Today, I am completing my Ph.D. in Neuroscience at [McGill University](https://www.mcgill.ca/ipn/) and the [Montreal Neurological Institute](https://www.mcgill.ca/neuro/), institutions that have shaped the work of great scientists like Brenda Milner and Wilder Penfield. My research explores the interaction between the auditory cortex and attention during learning and aging through the use of neuroimaging (EEG, MEG, MRI), behavioral measures and statistical analyses. 

I created this website as a space to share my research, experiences, and personal interests. Whether you are here for science, curiosity, or simply to get to know me a little better, I hope you find something that inspires you and sparks your curiosity.

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