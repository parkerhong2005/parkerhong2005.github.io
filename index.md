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
    <button class="carousel-arrow left-arrow">&#10094;</button>
    <!-- Carousel container -->
    <div class="carousel-container">
      {% for project in site.projects limit:9 %}
        <div class="carousel-item">
          {% include project-card.html 
            image="{{ project.image }}" 
            title="{{ project.title }}" 
            description="{{ project.description }}" %}
        </div>
      {% endfor %}
    </div>
    <!-- Right arrow -->
    <button class="carousel-arrow right-arrow">&#10095;</button>
    </div>
  </section>
</main>

<script>
document.addEventListener("DOMContentLoaded", () => {
  const container = document.querySelector(".carousel-container");
  const leftArrow = document.querySelector(".left-arrow");
  const rightArrow = document.querySelector(".right-arrow");

  const scrollAmount = 320; // pixels to scroll per click, adjust for your card width + gap

  leftArrow.addEventListener("click", () => {
    container.scrollBy({ left: -scrollAmount, behavior: "smooth" });
  });

  rightArrow.addEventListener("click", () => {
    container.scrollBy({ left: scrollAmount, behavior: "smooth" });
  });
});
</script>
