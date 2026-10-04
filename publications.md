---
layout: default
nav: publications
title: Publications
---
<section class="section first-section"><div class="container">
  <div class="page-tools"><a class="button primary" href="{{ site.author.scholar }}" target="_blank" rel="noopener">Google Scholar</a><a class="button" href="{{ site.author.orcid }}" target="_blank" rel="noopener">ORCID</a></div>
  <p class="pub-legend">My name is shown in <strong>bold</strong>. <strong>*</strong> denotes corresponding author; <strong>#</strong> denotes co-first author (equal contribution).</p>
{% assign pubs = site.data.publications %}
  {% assign years = pubs | map: 'year' | uniq %}
  {% for year in years %}
    <h2 class="year-heading">{{ year }}</h2>
    <div class="pub-list">
    {% for pub in pubs %}{% if pub.year == year %}
      <article class="pub">
        <p class="pub-title">{% if pub.url %}<a href="{{ pub.url }}" target="_blank" rel="noopener">{{ pub.title }}</a>{% else %}{{ pub.title }}{% endif %}</p>
        {% assign author_line = pub.authors %}
        {% if pub.corresponding and pub.cofirst %}
          {% assign author_line = author_line | replace: 'Weiyi Pan', '<strong>Weiyi Pan*#</strong>' %}
        {% elsif pub.corresponding %}
          {% assign author_line = author_line | replace: 'Weiyi Pan', '<strong>Weiyi Pan*</strong>' %}
        {% elsif pub.cofirst %}
          {% assign author_line = author_line | replace: 'Weiyi Pan', '<strong>Weiyi Pan#</strong>' %}
        {% else %}
          {% assign author_line = author_line | replace: 'Weiyi Pan', '<strong>Weiyi Pan</strong>' %}
        {% endif %}
        <p class="pub-authors">{{ author_line }}</p>
        <p class="pub-venue">{{ pub.venue }}{% if pub.note %} · {{ pub.note }}{% endif %}</p>
      </article>
    {% endif %}{% endfor %}
    </div>
  {% endfor %}
</div></section>
