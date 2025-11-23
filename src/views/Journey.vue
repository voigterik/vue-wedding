<script setup></script>
<template>
  <section id="journey" class="journey">
    <h2>Our Journey</h2>
    <section class="photos">
      <div class="polaroid">
        <img src="https://placehold.co/300x300" alt="Photo 1" />
        <p>Our first date</p>
      </div>
      <div class="polaroid">
        <img src="https://placehold.co/300x300" alt="Photo 2" />
        <p>The proposal</p>
      </div>
      <div class="polaroid">
        <img src="https://placehold.co/300x300" alt="Photo 3" />
        <p>Happy together</p>
      </div>
    </section>
  </section>
</template>

<style scoped>
.journey {
  position: relative;
  min-height: 100vh;
  padding: 2rem 2rem 3rem 2rem;
}

h2 {
  margin-bottom: 3rem;
  text-align: center;
}

.photos {
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  justify-content: center;
  align-items: center;
}

.polaroid {
  background: white;
  padding: 1rem 1rem 3rem 1rem;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  transition:
    transform 0.3s ease,
    box-shadow 0.3s ease;
}

.polaroid:nth-child(1) {
  transform: rotate(-3deg);
}

.polaroid:nth-child(2) {
  transform: rotate(2deg);
}

.polaroid:nth-child(3) {
  transform: rotate(-2deg);
}

.polaroid:hover {
  transform: rotate(0deg) scale(1.1);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3);
  z-index: 1;
}

.polaroid img {
  width: 100%;
  height: auto;
  display: block;
}

.polaroid p {
  text-align: center;
  margin-top: 1rem;
  font-family: "Playfair", serif;
  color: var(--color-text);
  font-size: 1.1rem;
}

@media (max-width: 768px) {
  .polaroid {
    max-width: 250px;
  }
}
</style>
