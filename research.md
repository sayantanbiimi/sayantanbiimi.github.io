---
layout: default
title: "Research | Sayantan Banerjee"
permalink: /research/
---

<div class="container academic-page">
  <p class="eyebrow-academic">Scholarship</p>
  <h1>Research &amp; publications</h1>
  <p class="page-lead">Bayesian statistical theory, high-dimensional inference, graphical models and modern methodology.</p>

  <nav class="research-nav" aria-label="Research sections">
    <a href="#research-interests">Research Interests</a>
    <a href="#publications">Journal Publications</a>
    <a href="#grants">Research Grants</a>
    <a href="#book-chapters">Book Chapters</a>
    <a href="#working-papers">Working Papers</a>
    <a href="#doctoral-students">Doctoral Students</a>
  </nav>

  <section class="academic-section" id="research-interests">
    <h2>Research interests</h2>
    <div class="research-tags">
      {% for x in site.data.interests %}
      <span>{{ x }}</span>
      {% endfor %}
    </div>
  </section>

  <section class="academic-section" id="publications">
    <div class="section-heading">
      <h2>Journal publications</h2>
      <span>{{ site.data.publications.size }} entries</span>
    </div>
    <div class="filter-row">
      <label for="pub-search">Search publications</label>
      <input type="search" id="pub-search" placeholder="Title, author, journal or year">
      <label for="pub-year">Year</label>
      <select id="pub-year">
        <option value="all">All years</option>
        {% assign years = site.data.publications | map: 'year' | uniq | sort | reverse %}
        {% for year in years %}
        <option value="{{ year }}">{{ year }}</option>
        {% endfor %}
      </select>
    </div>
    {% assign pubs = site.data.publications | sort: 'year' | reverse %}
    {% for pub in pubs %}
    <article class="simple-entry pub-entry" data-year="{{ pub.year }}">
      <span class="entry-date">{{ pub.year }}</span>
      <div>
        <h3>{{ pub.title }}</h3>
        <p>{{ pub.authors }}</p>
        <p><em>{{ pub.journal }}</em></p>
        {% if pub.url and pub.url != '' %}
        <a href="{{ pub.url }}" target="_blank" rel="noopener noreferrer">Find paper ↗</a>
        {% endif %}
      </div>
    </article>
    {% endfor %}
    <p id="no-pubs" hidden>No matching publications.</p>
  </section>

  <section class="academic-section" id="grants">
    <h2>Research grants</h2>
    <div class="academic-entry-list">
      {% for g in site.data.grants %}
      <article class="academic-entry dated-entry">
        <span class="entry-date">{{ g.period }}</span>
        <div class="entry-body">
          <h3>{{ g.title }}</h3>
          <p>{{ g.description }}</p>
        </div>
      </article>
      {% endfor %}
    </div>
  </section>

  <section class="academic-section" id="book-chapters">
    <h2>Book chapters</h2>
    <div class="academic-entry-list">
      {% for p in site.data.book_chapters %}
      <article class="academic-entry">
        <div class="entry-body">
          <h3>{{ p.title }}</h3>
          <p>{{ p.details }}</p>
          {% if p.url and p.url != '' %}
          <a href="{{ p.url }}" target="_blank" rel="noopener noreferrer">Find chapter ↗</a>
          {% endif %}
        </div>
      </article>
      {% endfor %}
    </div>
  </section>

  <section class="academic-section" id="working-papers">
    <h2>Working papers</h2>
    <div class="academic-entry-list working-papers-list">
      {% for p in site.data.working_papers %}
      <article class="academic-entry work-item">
        <div class="entry-body">
          <h3>{{ p.title }}</h3>
          {% if p.authors and p.authors != '' %}
          <p>{{ p.authors }}</p>
          {% endif %}
        </div>
      </article>
      {% endfor %}
    </div>
  </section>

  <section class="academic-section" id="doctoral-students">
    <h2>Current doctoral students</h2>
    <div class="academic-entry-list">
      {% for s in site.data.students %}
      <article class="academic-entry">
        <div class="entry-body">
          <h3>{{ s.name }}</h3>
          <p>{{ s.description }}</p>
        </div>
      </article>
      {% endfor %}
    </div>
  </section>
</div>

<script>
document.addEventListener('DOMContentLoaded', function () {
  const q = document.getElementById('pub-search');
  const y = document.getElementById('pub-year');
  const entries = Array.from(document.querySelectorAll('.pub-entry'));
  const noPubs = document.getElementById('no-pubs');

  function update() {
    const term = q.value.trim().toLowerCase();
    let count = 0;
    entries.forEach(function (entry) {
      const matches = entry.textContent.toLowerCase().includes(term) &&
        (y.value === 'all' || entry.dataset.year === y.value);
      entry.hidden = !matches;
      if (matches) count++;
    });
    noPubs.hidden = count !== 0;
  }

  q.addEventListener('input', update);
  y.addEventListener('change', update);
  update();
});
</script>
