---
layout: page
title: Publications
subtitle: Our contributions to cancer metabolism research
permalink: /publications/
---

{% assign pubs = site.data.publications | sort: 'year' | reverse %}
{% assign highlighted = pubs | where: "highlight", true %}
{% assign years = pubs | map: 'year' | uniq | sort | reverse %}

<!-- Featured Publications -->
{% if highlighted.size > 0 %}
<h2 style="margin-bottom: var(--space-6);"><i class="fas fa-star" style="color: var(--color-accent); margin-right: 8px;"></i> Featured Publications</h2>

<div class="publications-list" style="margin-bottom: var(--space-12);">
  {% for pub in highlighted %}
  <div class="publication-item" style="border-left-color: var(--color-warning);">
    <div class="publication-title">{{ pub.title }}</div>
    <div class="publication-authors">{{ pub.authors }}</div>
    <div class="publication-journal">
      <em>{{ pub.journal }}</em>{% if pub.volume %} <strong>{{ pub.volume }}</strong>{% endif %}{% if pub.pages %}, {{ pub.pages }}{% endif %} ({{ pub.year }})
    </div>
    <div class="publication-links">
      {% if pub.doi %}
        <a href="https://doi.org/{{ pub.doi }}" target="_blank" rel="noopener">
          <i class="fas fa-external-link-alt"></i> DOI
        </a>
      {% endif %}
      {% if pub.pmid %}
        <a href="https://pubmed.ncbi.nlm.nih.gov/{{ pub.pmid }}" target="_blank" rel="noopener">
          <i class="fas fa-book-medical"></i> PubMed
        </a>
      {% endif %}
      {% if pub.pdf %}
        <a href="{{ pub.pdf | relative_url }}" target="_blank">
          <i class="fas fa-file-pdf"></i> PDF
        </a>
      {% endif %}
    </div>
  </div>
  {% endfor %}
</div>
{% endif %}

<!-- All Publications by Year -->
<h2 style="margin-bottom: var(--space-6);">All Publications</h2>

{% for year in years %}
<h3 class="publication-year">{{ year }}</h3>

<div class="publications-list" style="margin-bottom: var(--space-8);">
  {% assign year_pubs = pubs | where: 'year', year %}
  {% for pub in year_pubs %}
  <div class="publication-item">
    <div class="publication-title">{{ pub.title }}</div>
    <div class="publication-authors">{{ pub.authors }}</div>
    <div class="publication-journal">
      <em>{{ pub.journal }}</em>{% if pub.volume %} <strong>{{ pub.volume }}</strong>{% endif %}{% if pub.pages %}, {{ pub.pages }}{% endif %}
    </div>
    <div class="publication-links">
      {% if pub.doi %}
        <a href="https://doi.org/{{ pub.doi }}" target="_blank" rel="noopener">
          <i class="fas fa-external-link-alt"></i> DOI
        </a>
      {% endif %}
      {% if pub.pmid %}
        <a href="https://pubmed.ncbi.nlm.nih.gov/{{ pub.pmid }}" target="_blank" rel="noopener">
          <i class="fas fa-book-medical"></i> PubMed
        </a>
      {% endif %}
      {% if pub.pdf %}
        <a href="{{ pub.pdf | relative_url }}" target="_blank">
          <i class="fas fa-file-pdf"></i> PDF
        </a>
      {% endif %}
    </div>
  </div>
  {% endfor %}
</div>
{% endfor %}

---

<div style="background: var(--color-gray-100); padding: var(--space-6); border-radius: var(--border-radius-lg); margin-top: var(--space-8);">
  <h3 style="margin-bottom: var(--space-3);"><i class="fas fa-graduation-cap" style="color: var(--color-accent); margin-right: 8px;"></i> Find Us Online</h3>
  <p style="margin-bottom: var(--space-4);">For a complete list of publications, visit:</p>
  <div style="display: flex; gap: var(--space-4); flex-wrap: wrap;">
    <a href="https://pubmed.ncbi.nlm.nih.gov/?term=Lukey+MJ" target="_blank" rel="noopener" class="btn btn-primary">
      <i class="fas fa-book-medical" style="margin-right: 8px;"></i> PubMed
    </a>
  </div>
</div>
