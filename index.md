---
layout: default
title: Home
---

<main class="home-page">
  <section class="hero">
    <div class="hero-content">
      <h1>Hi, I’m Parker Hong</h1>
      <p>Engineer | Designer | Leader</p>
      <a href="#projects" class="btn-primary">View Projects</a>
    </div>
  </section>

  <section class="intro">
    <h2>About Me</h2>
    <p>
      My name is Parker Hong and I'm a junior at Northwestern University from Chicago, Illinois. I am currently majoring in Manufacturing and Design Engineering and pursuing a minor in Architectural Engineering and Design.
    </p>
  </section>

  <!-- FEATURED PROJECTS CAROUSEL -->
<section id="projects" class="projects-carousel">
  <h2>Featured Projects</h2>
  <div class="carousel-wrapper">  
    <!-- Left arrow -->
    <!-- Left arrow -->
    <button class="carousel-arrow left-arrow" aria-label="Previous project">
      <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="var(--color-red)" stroke-width="3" stroke-linecap="round" stroke-linejoin="round">
        <polyline points="15 18 9 12 15 6"></polyline>
      </svg>
    </button>

    <!-- Carousel container -->
    <div class="carousel-container">
      {% assign sorted_projects = site.projects | sort: "order" %}
      {% for project in sorted_projects limit:9 %}
        <div class="carousel-item">
          {% include project-card.html image=project.image title=project.title description=project.short_description %}
        </div>
      {% endfor %}
    </div>

    <!-- Right arrow -->
    <button class="carousel-arrow right-arrow" aria-label="Next project">
      <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="var(--color-red)" stroke-width="3" stroke-linecap="round" stroke-linejoin="round">
        <polyline points="9 18 15 12 9 6"></polyline>
      </svg>
    </button>
  </div>
</section>

<!-- Carousel script -->
<script>
const leftArrow = document.querySelector('.left-arrow');
const rightArrow = document.querySelector('.right-arrow');
const carousel = document.querySelector('.carousel-container');

const scrollAmount = 320; // distance to scroll per click (adjust to card width + gap)

leftArrow.addEventListener('click', () => {
  carousel.scrollBy({ left: -scrollAmount, behavior: 'smooth' });
});

rightArrow.addEventListener('click', () => {
  carousel.scrollBy({ left: scrollAmount, behavior: 'smooth' });
});
</script>
</main>
