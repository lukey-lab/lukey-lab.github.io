---
layout: page
title: Our Team
subtitle: Meet the researchers driving discoveries in cancer metabolism
permalink: /team/
---

{% assign team = site.data.team %}
{% assign pi = team | where: "category", "pi" | first %}
{% assign postdocs = team | where: "category", "postdoc" %}
{% assign graduates = team | where: "category", "graduate" %}
{% assign undergrads = team | where: "category", "undergraduate" %}
{% assign staff = team | where: "category", "staff" %}
{% assign alumni = team | where: "category", "alumni" %}

<!-- Principal Investigator -->
<div class="pi-card" style="margin-bottom: var(--space-16);">
  <div class="pi-photo">
    <img src="{{ pi.photo | default: '/assets/images/team/placeholder.jpg' | relative_url }}" alt="{{ pi.name }}">
  </div>
  <div class="pi-info">
    <h2>{{ pi.name }}, Ph.D.</h2>
    <p class="pi-title">{{ pi.role }}</p>
    <p>{{ pi.bio }}</p>

    {% if pi.education %}
    <h4 style="margin-top: var(--space-6); margin-bottom: var(--space-2);">Education</h4>
    <ul style="margin-bottom: var(--space-4);">
      {% for edu in pi.education %}
        <li>{{ edu }}</li>
      {% endfor %}
    </ul>
    {% endif %}

    <div class="team-links" style="justify-content: flex-start; margin-top: var(--space-4);">
      {% if pi.email %}
        <a href="mailto:{{ pi.email }}" title="Email"><i class="fas fa-envelope"></i></a>
      {% endif %}
      {% if pi.twitter %}
        <a href="https://twitter.com/{{ pi.twitter }}" target="_blank" title="Twitter"><i class="fab fa-twitter"></i></a>
      {% endif %}
      {% if pi.google_scholar %}
        <a href="{{ pi.google_scholar }}" target="_blank" title="Google Scholar"><i class="fas fa-graduation-cap"></i></a>
      {% endif %}
      {% if pi.orcid %}
        <a href="https://orcid.org/{{ pi.orcid }}" target="_blank" title="ORCID"><i class="fab fa-orcid"></i></a>
      {% endif %}
    </div>
  </div>
</div>

{% if postdocs.size > 0 %}
<!-- Postdoctoral Fellows -->
<h2 style="margin-bottom: var(--space-8);">Postdoctoral Fellows</h2>
<div class="team-grid" style="margin-bottom: var(--space-16);">
  {% for member in postdocs %}
  <div class="card team-card hover-lift" style="padding: var(--space-6);">
    <div class="team-photo">
      <img src="{{ member.photo | default: '/assets/images/team/placeholder.jpg' | relative_url }}" alt="{{ member.name }}">
    </div>
    <h3 class="team-name">{{ member.name }}</h3>
    <p class="team-role">{{ member.role }}</p>
    <p class="team-bio">{{ member.bio }}</p>
    <div class="team-links">
      {% if member.email %}
        <a href="mailto:{{ member.email }}" title="Email"><i class="fas fa-envelope"></i></a>
      {% endif %}
      {% if member.twitter %}
        <a href="https://twitter.com/{{ member.twitter }}" target="_blank" title="Twitter"><i class="fab fa-twitter"></i></a>
      {% endif %}
      {% if member.google_scholar %}
        <a href="{{ member.google_scholar }}" target="_blank" title="Google Scholar"><i class="fas fa-graduation-cap"></i></a>
      {% endif %}
    </div>
  </div>
  {% endfor %}
</div>
{% endif %}

{% if graduates.size > 0 %}
<!-- Graduate Students -->
<h2 style="margin-bottom: var(--space-8);">Graduate Students</h2>
<div class="team-grid" style="margin-bottom: var(--space-16);">
  {% for member in graduates %}
  <div class="card team-card hover-lift" style="padding: var(--space-6);">
    <div class="team-photo">
      <img src="{{ member.photo | default: '/assets/images/team/placeholder.jpg' | relative_url }}" alt="{{ member.name }}">
    </div>
    <h3 class="team-name">{{ member.name }}</h3>
    <p class="team-role">{{ member.role }}</p>
    <p class="team-bio">{{ member.bio }}</p>
    <div class="team-links">
      {% if member.email %}
        <a href="mailto:{{ member.email }}" title="Email"><i class="fas fa-envelope"></i></a>
      {% endif %}
      {% if member.twitter %}
        <a href="https://twitter.com/{{ member.twitter }}" target="_blank" title="Twitter"><i class="fab fa-twitter"></i></a>
      {% endif %}
    </div>
  </div>
  {% endfor %}
</div>
{% endif %}

{% if undergrads.size > 0 %}
<!-- Undergraduate Students -->
<h2 style="margin-bottom: var(--space-8);">Undergraduate Students</h2>
<div class="team-grid" style="margin-bottom: var(--space-16);">
  {% for member in undergrads %}
  <div class="card team-card hover-lift" style="padding: var(--space-6);">
    <div class="team-photo">
      <img src="{{ member.photo | default: '/assets/images/team/placeholder.jpg' | relative_url }}" alt="{{ member.name }}">
    </div>
    <h3 class="team-name">{{ member.name }}</h3>
    <p class="team-role">{{ member.role }}</p>
    <p class="team-bio">{{ member.bio }}</p>
  </div>
  {% endfor %}
</div>
{% endif %}

{% if staff.size > 0 %}
<!-- Staff -->
<h2 style="margin-bottom: var(--space-8);">Staff</h2>
<div class="team-grid" style="margin-bottom: var(--space-16);">
  {% for member in staff %}
  <div class="card team-card hover-lift" style="padding: var(--space-6);">
    <div class="team-photo">
      <img src="{{ member.photo | default: '/assets/images/team/placeholder.jpg' | relative_url }}" alt="{{ member.name }}">
    </div>
    <h3 class="team-name">{{ member.name }}</h3>
    <p class="team-role">{{ member.role }}</p>
    <p class="team-bio">{{ member.bio }}</p>
    <div class="team-links">
      {% if member.email %}
        <a href="mailto:{{ member.email }}" title="Email"><i class="fas fa-envelope"></i></a>
      {% endif %}
    </div>
  </div>
  {% endfor %}
</div>
{% endif %}

{% if alumni.size > 0 %}
<!-- Alumni -->
<h2 style="margin-bottom: var(--space-8);">Alumni</h2>
<div class="publications-list">
  {% for member in alumni %}
  <div class="publication-item">
    <div class="publication-title">{{ member.name }}</div>
    <div class="publication-authors">{{ member.role }}</div>
    {% if member.current_position %}
    <div class="publication-journal">Now: {{ member.current_position }}</div>
    {% endif %}
  </div>
  {% endfor %}
</div>
{% endif %}
