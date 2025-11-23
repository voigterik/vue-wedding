<script setup></script>
<template>
  <section id="travel" class="details">
    <h2>Travel & Accomodation</h2>
    <section class="travel">
      <h3>Travel</h3>
      <p>Sicut malus movie horror.</p>
      <p>
        Zombies reversus ab inferno, nam malum cerebro. De carne animata corpora quaeritis. Summus
        sit​​, morbo vel maleficia?
      </p>
      <p>
        De Apocalypsi undead dictum mauris. Hi mortuis soulless creaturas, imo monstra adventus
        vultus comedat cerebella viventium.
      </p>
      <h3>Accomodation</h3>
      <p>
        De Apocalypsi undead dictum mauris. Hi mortuis soulless creaturas, imo monstra adventus
        vultus comedat cerebella viventium.
      </p>
      <h3>Gifts</h3>
      <p>
        De Apocalypsi undead dictum mauris. Hi mortuis soulless creaturas, imo monstra adventus
        vultus comedat cerebella viventium.
      </p>
    </section>
  </section>
</template>

<style scoped>
.details {
  position: relative;
  min-height: 100vh;
  padding: 2rem;
  text-align: center;
}

h2 {
  margin-bottom: 3rem;
}

p {
  margin: 1rem 0 2rem 0;
}

.team {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 3rem;
  margin: 3rem 0 0 0;
}

.person {
  margin-bottom: 3rem;
}

.profile {
  max-width: 100px;
  margin-bottom: 1rem;
  padding: 0.125rem;
  display: inline-block;
  border-radius: 50%;
  border: 1px solid var(--color-secondary);
  transition: filter 1s;
  filter: grayscale(100%);
}

.profile:hover {
  filter: grayscale(0);
}
</style>
