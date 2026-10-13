---
layout: default
title: "Contact | Sayantan Banerjee"
permalink: /contact/
---
<div class="container academic-page"><p class="eyebrow-academic">Contact</p><h1>Contact</h1>{% for section in site.data.contact %}<section class="academic-section" id="{{ section.id }}"><h2>{{ section.title }}</h2>{{ section.html }}</section>{% endfor %}</div>