<script setup>
import { ref, onMounted, onUnmounted } from "vue";
const isOpen = ref(false);
const isFloating = ref(false);

function toggleMenu() {
  isOpen.value = !isOpen.value;
}

function closeMenu() {
  isOpen.value = false;
}

function handleResize() {
  if (window.innerWidth > 768) {
    isOpen.value = false;
  }
}

function moveHeader() {
  window.scrollY > 70 ? (isFloating.value = true) : (isFloating.value = false);
  isOpen.value = false;
}

onMounted(() => {
  window.addEventListener("resize", handleResize);
  window.addEventListener("scroll", moveHeader);
});

onUnmounted(() => {
  window.removeEventListener("resize", handleResize);
  window.removeEventListener("scroll", moveHeader);
});
</script>
<template>
  <header id="top">
    <div class="header-container" :class="{ 'is-floating': isFloating }">
      <nav>
        <a href="#top" title="Back to top">
          <img src="https://placehold.co/60x40" alt="Back to the top" />
        </a>
        <ul class="menu" :class="{ 'is-open': isOpen }">
          <li>
            <a href="#journey" title="Our Journey" @click="closeMenu">Our Journey</a>
          </li>
          <li>
            <a href="#details" title="Details">Details</a>
          </li>
          <li>
            <a href="#travel" title="Travel & Stay">Travel & Stay</a>
          </li>
          <!-- <li>
            <a href="javascript:;" title="Dress Code">Dress Code</a>
          </li> -->
          <li>
            <a href="#faq" title="Frequently asked questions">FAQ</a>
          </li>
          <!-- <li>
            <a href="javascript:;" title="Contact">Contact</a>
          </li> -->
          <li>
            <a href="#rsvp" title="RSVP">RSVP</a>
          </li>
        </ul>
        <svg
          ref="hamburgerIcon"
          width="15"
          height="12"
          viewBox="0 0 15 12"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
          :class="{ open: isOpen }"
          @click="toggleMenu"
        >
          <line
            class="line line1"
            x1="0"
            y1="1"
            x2="15"
            y2="1"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
          />
          <line
            class="line line2"
            x1="0"
            y1="6"
            x2="15"
            y2="6"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
          />
          <line
            class="line line3"
            x1="0"
            y1="11"
            x2="15"
            y2="11"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
          />
        </svg>
      </nav>
    </div>
  </header>
</template>

<style scoped>
header {
  position: relative;
  z-index: 2;
  min-height: 70px;
  padding: 1rem;
  background: var(--color-page-background);
}

.header-container.is-floating {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 3;
  right: 0;
  padding: 0.5rem 1rem;
  background: var(--color-page-background);
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  animation: slideDown 0.4s ease-out forwards;
}

.header-container:not(.is-floating) {
  animation: none;
}

@keyframes slideDown {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

nav {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}

.menu {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  margin-left: auto;
  list-style: none;
}

.menu.m-show {
  display: flex;
}

.menu.m-hide {
  display: none;
}

.menu li {
  align-content: center;
  white-space: nowrap;
}

svg {
  display: flex;
  align-self: center;
  margin-left: auto;
  color: var(--color-primary);
  cursor: pointer;
  transition: color 0.3s ease;
}

svg:hover {
  color: var(--color-secondary);
}

svg .line {
  transition: all 0.3s ease;
  transform-origin: center;
}

.open .line1 {
  transform: rotate(45deg) translateY(5px);
}

.open .line2 {
  opacity: 0;
}

.open .line3 {
  transform: rotate(-45deg) translateY(-5px);
}

@media (max-width: 768px) {
  .menu {
    display: none;
    position: absolute;
    top: 100%;
    left: 0;
    z-index: 2;
    width: 100%;
    flex-direction: column;
    align-items: center;
    background: var(--color-page-background);
  }
  .menu.is-open {
    display: flex;
  }
  .menu li {
    margin: 1rem 0;
    font-size: 1.5rem;
  }
  svg {
    display: block;
  }
}
@media (min-width: 769px) {
  .menu {
    flex-direction: row;
  }
  svg {
    display: none;
  }
}
</style>
