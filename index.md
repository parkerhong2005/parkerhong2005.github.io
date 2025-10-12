---
layout: default
title: Home
---

<main class="home-page">
  <section class="hero">
    <div class="hero-content">
      <h1>Parker Hong</h1>
      <p>Design | Prototyping | User Experience</p>
    </div>
  </section>

  <section class="intro">
    <h2>About Me</h2>
    <p>
      I'm a junior at Northwestern University majoring in Manufacturing and Design Engineering (MaDE) and pursuing a minor in Architectural Engineering and Design. I am interested in the rapid prototyping process, computer-aided design (CAD), and the user experience (UX) side of engineering. Check out my projects past, present, and future, and feel free to reach out!
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
