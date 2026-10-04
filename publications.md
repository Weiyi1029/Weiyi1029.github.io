---
layout: default
nav: publications
title: Publications
---
<section class="section first-section"><div class="container">
  <div class="page-tools"><a class="button primary" href="{{ site.author.scholar }}" target="_blank" rel="noopener">Google Scholar</a><a class="button" href="{{ site.author.orcid }}" target="_blank" rel="noopener">ORCID</a></div>
{% assign pubs = site.data.publications %}
  {% assign years = pubs | map: 'year' | uniq %}
  {% for year in years %}
    <h2 class="year-heading">{{ year }}</h2>
    <div class="pub-list">
    {% for pub in pubs %}{% if pub.year == year %}
      <article class="pub">
        <p class="pub-title">{% if pub.url %}<a href="{{ pub.url }}" target="_blank" rel="noopener">{{ pub.title }}</a>{% else %}{{ pub.title }}{% endif %}</p>
        <p class="pub-authors">{{ pub.authors }}</p>
        <p class="pub-venue">{{ pub.venue }}{% if pub.note %} · {{ pub.note }}{% endif %}</p>
      </article>
    {% endif %}{% endfor %}
    </div>
  {% endfor %}
</div></section>
