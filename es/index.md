---
layout: default
title: "Home"
permalink: /es/
lang: es
---

# ¡Bienvenida a mi sitio web!

Mi nombre es Zaida. Nací en la Ciudad de México, en México, y desde muy pequeña, me fascinaba la complejidad de la vida. A los 12 años, una profesora nos pidió que diseñáramos nuestro plan de vida, y con mucha emoción, escribí que me convertiría en bióloga marina y que estudiaría un doctorado en el extranjero. Seguí ese plan durante mis estudios de licenciatura en Biología, en la [Universidad Nacional Autónoma de México](https://www.fciencias.unam.mx/). Sin embargo, en el camino, descubrí la neurociencia y me enamoré de ella, no solo por la complejidad del cerebro humano y su influencia en nuestro comportamiento, sino también por sus numerosas aplicaciones en la salud.

En agosto de 2025 completé mi doctorado en Neurociencia en la [Universidad de McGill](https://www.mcgill.ca/ipn/) y el [Instituto Neurológico de Montreal](https://www.mcgill.ca/neuro/), instituciones en las que científicos brillantes como Brenda Milner y Wilder Penfield desarrollaron sus grandes aportes a la ciencia. Mi proyecto doctoral exploró la interacción entre la corteza auditiva y la atención durante el aprendizaje y el envejecimiento, mediante el uso de técnicas de neuroimagen (EEG, MEG, MRI), medidas conductuales y análisis estadísticos. Si quieres saber más (y te atreves), puedes explorar [mi tesis doctoral]({{ "/assets/images/DoctoralThesis.pdf" | relative_url }}) o [las diapositivas de mi defensa]({{ "/assets/images/ThesisOralDefense.pdf" | relative_url}}).

Mientras completaba mi proyecto doctoral, me di cuenta de que quería tomar todo lo que había aprendido y aplicarlo a problemas que afectan de forma más directa a las personas, especialmente en salud y tecnología. En el proceso, desarrollé habilidades en diseño experimental, análisis de datos cuantitativos y cualitativos (R, Python, MATLAB, Excel) y modelación estadística (LMMs, GLMs, entre otros). Pero también exploré (y amé profundamente) los lados más creativos y prácticos de mi trabajo, desde construir este sitio web (errores incluidos) hasta diseñar recursos visuales (GIMP, Inkscape, Canva), e incluso usar y adaptar recursos de creadores como [Ross McConnell](https://2minutetabletop.com/author/2mtt/) para crear mis propios [mapas de campaña de DnD]({{"/assets/images/FullHouse-4-DungeonDraft.jpg" | relative_url}}) (Dungeondraft).

Disfruto mucho mejorar y automatizar procesos mediante código (Powershell, bash, Python) u otras herramientas (IA, Power Automate, Power Query, Windows Task Scheduler, Cron jobs, Git), simplemente para ahorrar tiempo y evitar repetir tareas que me resultan tediosas. También me gusta organizar ideas y proyectos usando herramientas de gestión de proyectos (Trello, diagramas de Gantt, Excel), y aplico eso a muchas áreas de mi vida, desde llevar el seguimiento de la salud de mis gatos ([Whisky]({{ "/assets/images/Whisky.jpg" | relative_url }}) y [Noam]({{ "/assets/images/Noam.jpg" | relative_url}})) hasta planear cómo será mi próximo jardín. Sin embargo, lo que más disfruto es el proceso de aprendizaje detrás de cada una de estas habilidades, así como entender ideas complejas y traducirlas a algo que cualquier persona pueda entender, usando gráficas, infografías o presentaciones.

Mientras sigo creciendo profesionalmente, mi meta es aplicar estas habilidades como analista de datos y coordinadora de proyectos de investigación en entornos académicos y de salud, con el objetivo a largo plazo de contribuir a decisiones de salud pública. Actualmente trabajo como coordinadora de investigación, especializada en análisis de datos, para el [Brain-Heart Interconnectome](https://www.uottawa.ca/research-innovation/bhi), una iniciativa muy padre de la Universidad de Ottawa que combina distintas disciplinas científicas para mejorar el diagnóstico, tratamiento y prevención de condiciones cerebrales y cardíacas. ¡Deberías de checarla!

Creé este sitio web como un espacio para compartir todas estas piezas de mi vida: desde mi trabajo y mi investigación, hasta los pequeños proyectos e ideas que quiero explorar en el camino. Ya sea que estés aquí por la ciencia, por curiosidad o simplemente para conocerme un poco más, espero que encuentres algo que te inspire y despierte tu curiosidad.

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