---
layout: default
title: "Home"
permalink: /en/
lang: en
---

# Welcome to my website!

My name is Zaida. I was born in Mexico City, Mexico, and from an early age, I was fascinated by the complexity of life. At 12 years old, a teacher asked us to design a life plan, and I eagerly wrote that I would become a marine biologist and pursue a Ph.D. abroad. I followed that vision during my undergraduate studies, majoring in Biology in the [National Autonomous University of Mexico](https://www.fciencias.unam.mx/). Along the way, I discovered neuroscience and fell in love with it, not only for the intricacies of the human brain and how it shapes our behavior, but also for its many applications in health.

In August 2025, I completed my Ph.D. in Neuroscience at [McGill University](https://www.mcgill.ca/ipn/) and the [Montreal Neurological Institute](https://www.mcgill.ca/neuro/), institutions that have shaped the work of great scientists like Brenda Milner and Wilder Penfield. My research explored the interaction between the auditory cortex and attention during learning and aging through the use of neuroimaging (EEG, MEG, MRI), behavioral measures and statistical analyses. If you want to learn more (and are brave enough), you can dive into [my doctoral thesis]() or through [my defence slides]({{ "/assets/images/ThesisOralDefense.pdf" | relative_url}}).

Throughout my doctoral project, I realized that I wanted to take what I had learned and apply it to problems that affect people more directly, especially in health and technology. Along the way, I developed skills in experimental design, quantitative and qualitative data analysis (R, Python, MATLAB, Excel) and statistical modelling (LMMs, GLMs, etc.). But I also explored (and loved deeply) more creative and practical sides of my work, from building this website (all errors included!) to designing visuals (GIMP, Inkscape, Canva) and even using and adapting assets from creators like [Ross McConnell](https://2minutetabletop.com/author/2mtt/) to create my own [DnD campaign maps]({{"/assets/images/FullHouse-4-DungeonDraft.jpg" | relative_url}}) (Dungeondraft).

I enjoy optimizing and automating processes through code (Powershell, bash, Python), or with other tools (AI, Power Automate, Power Query, Windows Task Scheduler, Cron jobs, Git), just to save time and avoid repeating tasks that I find boring. I also like organizing ideas and projects, using project management tools (Trello, Gantt charts, Excel), and I apply that to many areas of my life, from tracking my cats' ([Whisky]({{ "/assets/images/Whisky.jpg" | relative_url }}) and [Noam]({{ "/assets/images/Noam.jpg" | relative_url}})) health to planning what my next garden will look like. What I enjoy the most, though, is the learning process behind developing each of these skills, as well as understanding complex concepts and then translating them into something that anyone can understand, using graphics, dashboards, infographics or presentations.

As I continue to grow professionally, my goal is to apply these skills as a data analyst and research project coordinator in academic and healthcare settings, with the long-term aim of contributing to public health decisions. Today, I work as a research coordinator specializing in data analysis for the [Brain-Heart Interconnectome](https://www.uottawa.ca/research-innovation/bhi), a really cool initiative from the University of Ottawa that combines different fields and strategies to improve the diagnosis, treatment and prevention of brain and heart conditions. Go check it out!

I created this website as a space to bring all of these pieces together, from my research and technical work to the small projects and ideas that I enjoy exploring along the way. Whether you are here for science, curiosity, or simply to get to know me a little better, I hope you find something that inspires you and sparks your imagination.

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