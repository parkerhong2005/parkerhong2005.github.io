---
layout: default
title: "Projects"
permalink: /projects/
---
<h1>Projects</h1>
<div class="project-grid">
  {% for project in site.projects %}
  <div class="project-card">
    <a href="{{ project.url }}">
      <img src="{{ project.image }}" alt="{{ project.title }}" class="project-thumb" />
      <h2>{{ project.title }}</h2>
      <p>{{ project.description }}</p>
    </a>
  </div>
  {% endfor %}
</div>
