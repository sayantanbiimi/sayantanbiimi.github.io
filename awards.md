---
layout: default
title: "Honors & Awards | Sayantan Banerjee"
permalink: /awards/
---
<div class="container academic-page"><p class="eyebrow-academic">Recognition</p><h1>Honors & awards</h1><section class="academic-section">{% for a in site.data.awards %}<div class="simple-entry"><span class="entry-date">{{ a.date }}</span><div><h3>{{ a.title }}</h3></div></div>{% endfor %}</section></div>