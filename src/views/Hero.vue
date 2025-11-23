<script setup></script>
<template>
  <section class="hero">
    <div class="image"></div>
    <div class="text tenho">Tenho</div>
    <div class="text ampersand">&amp;</div>
    <div class="text myrna">Myrna</div>
  </section>
</template>

<style scoped>
.hero {
  position: relative;
  min-height: calc(100vh - 72px);
  overflow: hidden;
}

.image {
  position: absolute;
  z-index: -1;
  inset: 0;
  background: url(../assets/images/hero.jpg) center center no-repeat;
  background-size: cover;
  filter: blur(4px) grayscale(80%) contrast(1.8) brightness(0.8);
}

.text {
  position: absolute;
  font-family: "Playfair";
  font-size: calc(var(--h1-size) * 3);
  color: var(--color-secondary);
}

.tenho {
  top: -100%;
  left: 50%;
  margin-left: -138px;
  animation: tenhoSlide 3s 0.5s 1 normal forwards;
}
.ampersand {
  top: 42%;
  left: 50%;
  margin-left: -42px;
  opacity: 0;
  animation: ampersandSlide 1s 4s 1 normal forwards;
}
.myrna {
  left: 50%;
  bottom: -100%;
  margin-left: -143px;
  animation: myrnaSlide 3s 1s 1 normal forwards;
}

@keyframes tenhoSlide {
  0% {
    top: -100%;
  }
  100% {
    top: 30%;
  }
}

@keyframes myrnaSlide {
  0% {
    bottom: -100%;
  }
  100% {
    bottom: 27%;
  }
}

@keyframes ampersandSlide {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>
