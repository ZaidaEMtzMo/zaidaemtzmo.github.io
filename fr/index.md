---
layout: default
title: "Home"
permalink: /fr/
lang: fr
---

# Bienvenue sur mon site Web !

Je m’appelle Zaida. Je suis née à Mexico, au Mexique, et depuis mon enfance, j’ai été fascinée par la complexité des êtres vivants. À 12 ans, un enseignant nous a demandé de créer un plan de vie, et j’ai écrit avec enthousiasme que je deviendrais biologiste marine et que je poursuivrais un doctorat à l’étranger. J’ai commencé mes études en biologie à [l'Université Nationale Autonome du Mexique](https://www.fciencias.unam.mx/) avec cette vision. Mais au fil du chemin, j'ai découvert les neurosciences et je me suis passionnée pour ce domaine, non seulement pour la complexité du cerveau humain et son lien avec notre comportement, mais aussi pour ses nombreuses applications en santé publique.

Aujourd’hui, je suis en train de finir mon doctorat en neurosciences à [l'Université McGill](https://www.mcgill.ca/ipn/) et à [l'Institut Neurologique de Montréal](https://www.mcgill.ca/neuro/fr), des institutions où ont travaillé de grands scientifiques comme Brenda Milner et Wilder Penfield. Ma recherche étudie l’interaction entre le cortex auditif et l’attention pendant l’apprentissage et le vieillissement, en utilisant des techniques de neuroimagerie (EEG, MEG, MRI), des mesures comportementales et des analyses statistiques.

J’ai créé ce site web pour partager mes recherches, mes expériences et mes intérêts personnels. Que vous soyez ici par intérêt scientifique, par curiosité ou simplement pour mieux me connaître, j’espère que vous trouverez quelque chose qui vous inspirera et stimulera votre curiosité.

## Derniers Articles
{% assign filtered_posts = site.posts | where: "lang", page.lang | sort: "date" | reverse %}
{% assign post_count = filtered_posts | size %}

{% for post in filtered_posts limit:5 %}
  {% assign lang = post.lang | default: site.lang %}
  {% assign month_index = post.date | date: "%-m" | minus: 1 %}
  {% assign month_translated = site.months[lang][month_index] %}

  - [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "le %d" }} {{ month_translated }} {{ post.date | date: "%Y" }}
{% endfor %}

{% if post_count > 5 %}
  <p><a href="{{ site.nav_links[page.lang].AllPosts | relative_url }}">{{ site.data.translations[page.lang].view_all }}</a></p>
{% endif %}