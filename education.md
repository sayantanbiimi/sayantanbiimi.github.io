---
layout: default
title: "Education | Sayantan Banerjee"
permalink: /education/
---
<div class="container academic-page"><p class="eyebrow-academic">Education</p><h1>Education</h1>{% for section in site.data.education %}<section class="academic-section" id="{{ section.id }}"><h2>{{ section.title }}</h2>{{ section.html }}</section>{% endfor %}</div>