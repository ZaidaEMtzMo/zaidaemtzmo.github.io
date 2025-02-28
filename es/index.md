---
layout: default
title: "Home"
permalink: /es/
lang: es
---

# ¡Bienvenida a mi sitio web!

El objetivo de esta página es tener un espacio donde compartir mis pensamientos, intereses y los resultados de mi investigación.

## Entradas recientes
{% assign filtered_posts = site.posts | where: "lang", page.lang | sort: "date" | reverse %}
{% for post in filtered_posts limit:5 %}
  - [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%d de %B de %Y" }}
{% endfor %}