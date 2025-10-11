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
        <img src="{{ project.image }}" alt="{{ project.title }}" class="project-image" />
        <div class="project-overlay">
          <p class="project-tools">{{ project.tools }}</p>
          <p class="project-shortdesc">{{ project.short_description }}</p>
        </div>
      </div>
      <h2 class="project-title">{{ project.title }}</h2>
    </a>
  </div>
  {% endfor %}
</div>
