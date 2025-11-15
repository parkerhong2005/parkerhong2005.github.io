---
layout: default
title: "Projects"
permalink: /projects/
---

<h1>Projects</h1>

<p>
The following are a representation of classroom assignments, internship projects, and freelance design work. Each presented a unique set of design and problem-solving challenges. Click on a project icon to learn more about my work!
</p>

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

<style>
/* Project grid */
.project-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* always 3 columns */
  gap: 0.5rem; /* smaller spacing */
  width: 100%;
  padding: 0.5rem;
  box-sizing: border-box;
  justify-items: center;
  margin: 2rem auto;
}

/* Project card */
.project-card {
  position: relative;
  width: 100%;       /* fill grid cell */
  aspect-ratio: 1 / 1; /* square */
  overflow: hidden;
  border-radius: 12px;
  cursor: pointer;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  transition: transform 0.25s ease;
  display: flex;
  justify-content: center;
  align-items: center;
}

.project-card:hover {
  transform: scale(1.03);
}

/* Image wrapper */
.project-image-wrapper {
  width: 100%;
  height: 100%;
}

.project-image-wrapper img {
  width: 100%;
  height: 100%;
  object-fit: cover; /* fills the square */
  border-radius: 12px;
  display: block;
  transition: transform 0.3s ease;
}

/* Overlay */
.project-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center; /* vertical centering */
  text-align: center;
  background-color: rgba(0,0,0,0.6);
  color: #ffffff; /* white overlay text */
  opacity: 0;
  transition: opacity 0.3s ease;
  padding: 0.5rem;
}

.project-card:hover .project-overlay {
  opacity: 1;
}

.overlay-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 0.25rem;
}

.overlay-title {
  font-size: 1.1rem;
  font-weight: 700;
  margin-bottom: 0.25rem;
  color: #ffffff;
}

.overlay-desc {
  font-size: 0.9rem;
  line-height: 1.2;
  color: #ffffff;
}

/* Keep grid 3 columns on all devices */
@media (max-width: 1200px) {
  .project-grid { grid-template-columns: repeat(3, 1fr); }
}
@media (max-width: 900px) {
  .project-grid { grid-template-columns: repeat(3, 1fr); }
}
@media (max-width: 600px) {
  .project-grid { grid-template-columns: repeat(3, 1fr); }
}
</style>
