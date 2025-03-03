---
layout: default
title: "Home"
permalink: /es/
lang: es
---

# ¡Bienvenida a mi sitio web!

Mi nombre es Zaida. Nací en la Ciudad de México, en México, y desde muy pequeña, me fascinaba la complejidad de la vida. A los 12 años, una profesora nos pidió que diseñáramos nuestro plan de vida, y con mucha emoción, escribí que me convertiría en bióloga marina y que estudiaría un doctorado en el extranjero. Seguí ese plan durante mis estudios de licenciatura en Biología, en la [Universidad Nacional Autónoma de México](https://www.fciencias.unam.mx/). Sin embargo, a lo largo del camino, descubrí la neurociencia y me enamoré de ella, no solo por la complejidad del cerebro humano y su influencia en nuestro comportamiento, sino también por sus numerosas aplicaciones en la salud.

Hoy en día, estoy terminando mi doctorado en Neurociencia en la [Universidad de McGill](https://www.mcgill.ca/ipn/) y el [Instituto Neurológico de Montreal](https://www.mcgill.ca/neuro/), instituciones en las que científicos brillantes como Brenda Milner y Wilder Penfield han desarrollado grandes aportes a la ciencia. Mi proyecto de doctorado estudia la interacción entre la corteza auditiva y la atención durante el aprendizaje y el envejecimiento, mediante el uso de técnicas de neuroimagen (EEG, MEG, MRI), medidas conductuales y análisis estadísticos.

Creé este sitio web como un espacio para compartir mi investigación, mis experiencias e intereses personales. Ya sea que estés aquí por la ciencia, curiosidad o simplemente para conocerme un poco más, espero que encuentres algo que te inspire y despierte tu curiosidad.

## Entradas recientes
{% assign filtered_posts = site.posts | where: "lang", page.lang | sort: "date" | reverse %}
{% assign post_count = filtered_posts | size %}

{% for post in filtered_posts limit:5 %}
  {% assign lang = post.lang | default: site.lang %}
  {% assign month_index = post.date | date: "%-m" | minus: 1 %}
  {% assign month_translated = site.months[lang][month_index] %}

  - [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%d de" }} {{ month_translated }} {{ post.date | date: "de %Y" }}
{% endfor %}

{% if post_count > 5 %}
  <p><a href="{{ site.nav_links[page.lang].AllPosts | relative_url }}">{{ site.data.translations[page.lang].view_all }}</a></p>
{% endif %}