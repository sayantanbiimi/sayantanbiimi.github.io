---
layout: default
title: "Teaching | Sayantan Banerjee"
permalink: /teaching/
---
<div class="container academic-page"><p class="eyebrow-academic">In the classroom</p><h1>Teaching</h1><p class="page-lead">Courses in statistics, quantitative methods, and analytics across academic programmes.</p>{% for group in site.data.teaching %}<section class="academic-section" id="{{ group.id }}"><h2>{{ group.level }}</h2>{% for p in group.groups %}<h3>{{ p.program }}</h3><ul class="course-items">{% for c in p.courses %}<li>{{ c }}</li>{% endfor %}</ul>{% endfor %}</section>{% endfor %}</div>