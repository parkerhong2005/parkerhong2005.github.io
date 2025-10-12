---
layout: default
title: "Projects"
permalink: /projects/
---
<h1>Projects</h1>

<div class="project-grid">
  {% assign sorted_projects = site.projects | sort: "order" %}
  {% for project in sorted_projects %}
  <div class="project-card">
    <a href="{{ project.url }}">
      <div class="project-image-wrapper">
        <img src="{{ project.image }}" alt="{{ project.title }}" class="project-image" />
      </div>
      <div class="project-overlay">
        <div class="overlay-content">
          <h2 class="overlay-title">{{ project.title }}</h2>
          <p class="overlay-desc">{{ project.short_description }}</p>
          <div class="overlay-tools">
            {% for tool in project.tools %}
              <span class="tool-pill">{{ tool }}</span>
            {% endfor %}
          </div>
        </div>
      </div>
    </a>
  </div>
  {% endfor %}
</div>
