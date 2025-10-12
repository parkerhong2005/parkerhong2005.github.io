---
layout: default
title: Home
---

<main class="home-page">
  <section class="hero">
    <div class="hero-content">
      <h1>Parker Hong</h1>
      <p>Engineering | Design | Impact</p>
    </div>
  </section>

  <section class="intro">
    <h2>About Me</h2>
    <p>
      I'm a junior at Northwestern University from Chicago, Illinois. I am currently majoring in Manufacturing and Design Engineering and pursuing a minor in Architectural Engineering and Design.
    </p>
  </section>

  <!-- FEATURED PROJECTS CAROUSEL -->
<section id="projects" class="projects-carousel">
  <h2>My Projects</h2>
  <div class="carousel-wrapper">  
    <!-- Left arrow -->
    <button class="carousel-arrow left-arrow">&#10094;</button>
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
    <button class="carousel-arrow right-arrow">&#10095;</button>
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
