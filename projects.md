---
layout: default
title: "Projects"
permalink: /projects/
---

<style>
/*--------------------------------------------------------------
PROJECTS PAGE HEADER STYLING
--------------------------------------------------------------*/

/* Main Projects page title (<h1>) */
.project-page > .project-header h1 {
  font-size: 3rem;           /* bigger title */
  margin-top: 3rem;          /* space from top of page */
  margin-bottom: 1rem;       /* space below title */
  text-align: center;        /* center aligned */
}

/* Paragraph under main title */
.project-page > .project-header p {
  font-size: 1.1rem;         /* slightly bigger paragraph */
  margin: 0 auto 2rem auto;  /* top 0, bottom 2rem, centered */
  max-width: 800px;          /* optional: limit line length */
  text-align: center;
}

/* Extra spacing between header and project grid */
.project-page .project-grid {
  margin-top: 2rem;          /* adds space below paragraph */
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .project-page > .project-header h1 {
    font-size: 2.25rem;
    margin-top: 2rem;
  }

  .project-page > .project-header p {
    font-size: 1rem;
    margin-bottom: 1.5rem;
  }

  .project-page .project-grid {
    margin-top: 1.5rem;
  }
}
</style>

<div class="project-page">
  <div class="project-header">
    <h1>Projects</h1>
    <p>
      The following are a representation of classroom assignments, internship projects, and freelance design work. Each presented a unique set of design and problem-solving challenges. Click on a project icon to learn more about my work!
    </p>
  </div>

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
          </div>
        </div>
      </a>
    </div>
  {% endfor %}
</div>
