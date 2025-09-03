---
layout: page
permalink: /teaching/
title: Teaching & Outreach
description:
nav: true
nav_order: 6
---

<div class="row teach-igloo my-4" id="igloo-section">
  <!-- FULL-WIDTH TITLE -->
  <div class="col-12">
    <h3 class="mb-3 igloo-title">
      From Electrons to Igloos: The Molecular Foundations of Arctic Ingenuity
      <span class="subtitle">(Hong Kong Space Museum, 30 Aug 2025)</span>
    </h3>
  </div>

  <!-- TEXT (LEFT) -->
  <div class="col-md-6">
    <p class="justify">
      How does hydrogen bonding in water molecules relate to the history of humans in the Arctic? I had the privilege of speaking at the Hong Kong Space Museum as part of the “Unveiling the Arctic: Then and Now” Lecture Series, co-organised with the Geological Society of London Hong Kong Regional Group (GSL-HKRG). My talk, “From Electrons to Igloos: The Molecular Foundations of Arctic Ingenuity” (In Chinese:《從電子到雪屋：北極智慧的分子奧秘》), explored how the molecular arrangements of water molecules connect directly to Inuit ingenuity and development.
    </p>

    <p class="justify mb-2"><strong>Together, we looked at:</strong></p>
    <ul class="justify">
      <li>The history of Inuit and their migration across generations</li>
      <li>The phase diagram of water and its many exotic forms of ice</li>
      <li>Snow’s thermal conductivity and its role as a building material for igloos</li>
      <li>How these physical principles underpin the construction of igloos, and ultimately shape the resilience of Inuit populations</li>
    </ul>

    <p class="mt-3">
      <a class="btn btn-dark" href="/teaching/HKSM_talk" target="_blank" rel="noopener">VIEW THE LECTURE SLIDES →</a>
    </p>
  </div>

  <!-- SLIDESHOW (RIGHT) -->
  <div class="col-md-6">
    <div class="igloo-slider" id="iglooSlider1" aria-label="Igloo talk photo slideshow">
      <div class="igloo-track" data-track>
        <img src="/assets/img/teaching/Spacemuseum_Aug2025/arctic_cartoon.jpg" class="igloo-slide" alt="Cartoon illustration" loading="lazy">
        <img src="/assets/img/teaching/Spacemuseum_Aug2025/pic1.jpg" class="igloo-slide" alt="Talk photo 1" loading="lazy">
        <img src="/assets/img/teaching/Spacemuseum_Aug2025/pic2.jpg" class="igloo-slide" alt="Talk photo 2" loading="lazy">
        <img src="/assets/img/teaching/Spacemuseum_Aug2025/pic3.jpg" class="igloo-slide" alt="Talk photo 3" loading="lazy">
      </div>

      <!-- BIG, CLEAR ARROWS -->
      <button class="igloo-nav prev" type="button" aria-label="Previous photo" data-prev>‹</button>
      <button class="igloo-nav next" type="button" aria-label="Next photo" data-next>›</button>
    </div>
  </div>
</div>

<!-- Minimal self-contained JS -->
<script>
(function () {
  const slider = document.getElementById('iglooSlider1');
  if (!slider) return;
  const track = slider.querySelector('[data-track]');
  const slides = Array.from(track.children);
  let index = 0;

  function go(i) {
    index = (i + slides.length) % slides.length;
    track.scrollTo({ left: slides[index].offsetLeft, behavior: 'smooth' });
  }

  slider.querySelector('[data-prev]').addEventListener('click', function(){ go(index - 1); });
  slider.querySelector('[data-next]').addEventListener('click', function(){ go(index + 1); });

  // Keep index in sync when user swipes/scrolls
  let ticking = false;
  track.addEventListener('scroll', function () {
    if (ticking) return;
    requestAnimationFrame(function () {
      const mid = track.scrollLeft + track.clientWidth / 2;
      index = slides.reduce((best, _, i) => {
        const c = slides[i].offsetLeft + slides[i].clientWidth / 2;
        const cb = slides[best].offsetLeft + slides[best].clientWidth / 2;
        return Math.abs(c - mid) < Math.abs(cb - mid) ? i : best;
      }, 0);
      ticking = false;
    });
    ticking = true;
  });
})();
</script>

