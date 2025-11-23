<script setup>
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import Hero from "./views/Hero.vue";
import Journey from "./views/Journey.vue";
import Details from "./views/Details.vue";
import Travel from "./views/Travel.vue";
import FAQ from "./views/FAQ.vue";
import RSVP from "./views/RSVP.vue";
</script>

<template>
  <section>
    <Header />
    <main>
      <Hero />
      <Journey />
      <Details />
      <Travel />
      <FAQ />
      <RSVP />
    </main>
    <Footer />
  </section>
</template>

<style scoped></style>
