---
layout: default
title: Home
---

<main class="home-page">

  <!-- HERO / INTRO SECTION -->
  <section class="hero">
    <div class="hero-content">
      <div class="hero-image">
        <img src="/images/headshot.jpg" alt="Portrait of Parker Hong" class="hero-headshot">
      </div>
      <div class="hero-text">
        <h1>Parker Hong</h1>
        <h2>Manufacturing & Design Engineering (MaDE)</h2>
        <p>Northwestern University | Class of 2026</p>
        <p>Email: <a href="mailto:parkerhong@u.northwestern.edu">parkerhong@u.northwestern.edu</a></p>
        <p>LinkedIn: <a href="https://linkedin.com/in/parkerhong" target="_blank">linkedin.com/in/parkerhong</a></p>
      </div>
    </div>
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
    const scrollAmount = 320; // distance to scroll per click

    leftArrow.addEventListener('click', () => {
      carousel.scrollBy({ left: -scrollAmount, behavior: 'smooth' });
    });
    rightArrow.addEventListener('click', () => {
      carousel.scrollBy({ left: scrollAmount, behavior: 'smooth' });
    });
  </script>

</main>
