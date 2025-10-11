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
      <div class="project-image-wrapper">
        <img src="{{ project.image | relative_url }}" alt="{{ project.title }}" class="project-image" />
        <div class="project-overlay">
          <h2 class="overlay-title">{{ project.title }}</h2>
          <p class="overlay-desc">{{ project.short_description }}</p>
        </div>
      </div>
    </a>
  </div>
  {% endfor %}
</div>
