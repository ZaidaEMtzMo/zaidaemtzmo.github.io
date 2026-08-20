---
layout: default
title: "Home"
permalink: /fr/
lang: fr
---

# Bienvenue sur mon site Web !

Je m'appelle Zaida. Je suis née à Mexico, au Mexique, et depuis mon enfance, j'ai été fascinée par la complexité des êtres vivants. À 12 ans, un enseignant nous a demandé de créer un plan de vie, et j'ai écrit avec enthousiasme que je deviendrais biologiste marine et que je poursuivrais un doctorat à l'étranger. J'ai commencé mes études en biologie à [l'Université Nationale Autonome du Mexique](https://www.fciencias.unam.mx/) avec cette vision. Mais au fil du chemin, j'ai découvert les neurosciences et je me suis passionnée pour ce domaine, non seulement pour la complexité du cerveau humain et son lien avec notre comportement, mais aussi pour ses nombreuses applications en santé publique.

En août 2025, j'ai fini mon doctorat en neurosciences à [l'Université McGill](https://www.mcgill.ca/ipn/) et à [l'Institut Neurologique de Montréal](https://www.mcgill.ca/neuro/fr), des institutions où ont travaillé de grands scientifiques comme Brenda Milner et Wilder Penfield. Ma recherche a étudié l'interaction entre le cortex auditif et l'attention pendant l'apprentissage et le vieillissement, en utilisant des techniques de neuroimagerie (EEG, MEG, IRM), des mesures comportementales et des analyses statistiques. Si tu veux en savoir plus (et que tu es assez courageux·se), tu peux consulter [ma thèse de doctorat]({{ "/assets/images/DoctoralThesis.pdf" | relative_url }}) ou [les diapositives de ma soutenance]({{ "/assets/images/ThesisOralDefense.pdf" | relative_url}}).

Tout au long de mon projet de doctorat, je me suis rendu compte que je voulais mettre à profit ce que j'avais appris pour m'attaquer à des problèmes qui touchent les gens plus directement, notamment en santé et en technologie. En chemin, j'ai développé des compétences en conception expérimentale, en analyse de données quantitatives et qualitatives (R, Python, MATLAB, Excel) et en modélisation statistique (LMM, GLM, entre autres). Mais j'ai aussi exploré (et beaucoup aimé) les aspects plus créatifs et pratiques de mon travail, de la construction de ce site web (avec toutes ses erreurs) à la conception visuelle (GIMP, Inkscape, Canva), en passant par l'utilisation et l'adaptation de ressources de créateurs comme [Ross McConnell](https://2minutetabletop.com/author/2mtt/) pour créer mes propres [cartes de campagne DnD]({{"/assets/images/FullHouse-4-DungeonDraft.jpg" | relative_url}}) (Dungeondraft).

J'aime optimiser et automatiser des processus par le code (Powershell, bash, Python) ou avec d'autres outils (IA, Power Automate, Power Query, Windows Task Scheduler, tâches Cron, Git), simplement pour gagner du temps et éviter de répéter des tâches que je trouve ennuyeuses. J'aime aussi organiser des idées et des projets à l'aide d'outils de gestion de projet (Trello, diagrammes de Gantt, Excel), et j'applique cela à plusieurs aspects de ma vie, du suivi de la santé de mes chats ([Whisky]({{ "/assets/images/Whisky.jpg" | relative_url }}) et [Noam]({{ "/assets/images/Noam.jpg" | relative_url}})) à la planification de mon prochain jardin. Ce que j'aime le plus, cependant, c'est le processus d'apprentissage derrière chacune de ces compétences, ainsi que le fait de comprendre des concepts complexes et de les traduire en quelque chose que tout le monde peut comprendre, à l'aide de graphiques, de tableaux de bord, d'infographies ou de présentations.

Alors que je continue à progresser sur le plan professionnel, mon objectif est d'appliquer ces compétences en tant qu'analyste de données et coordonnatrice de projets de recherche dans des milieux académiques et de santé, avec pour objectif à long terme de contribuer aux décisions en matière de santé publique. Je travaille actuellement comme coordonnatrice de recherche, spécialisée en analyse de données, pour [l'Interconnectome cœur-cerveau](https://www.uottawa.ca/recherche-innovation/icc), un programme de recherche très intéressante de l'Université d'Ottawa qui combine différents domaines et stratégies pour améliorer le dépistage, le traitement et la prévention des troubles concomitants cérébraux et cardiaques. Vas-y jeter un coup d'œil !

J'ai créé ce site web comme un espace pour rassembler toutes ces facettes, de mes recherches et de mon travail technique aux petits projets et idées que j'aime explorer en chemin. Que tu sois ici par intérêt scientifique, par curiosité ou simplement pour mieux me connaître, j'espère que tu trouveras quelque chose qui t'inspirera et stimulera ta curiosité.

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