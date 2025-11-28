<script setup>
import { onMounted } from 'vue';
import TheHeader from './components/TheHeader.vue';
import TheHero from './components/TheHero.vue';
import TheFeatures from './components/TheFeatures.vue';
import TheMobileOffice from './components/TheMobileOffice.vue';
import TheStats from './components/TheStats.vue';
import TheFooter from './components/TheFooter.vue';

onMounted(() => {
  const observerOptions = {
    threshold: 0.1
  };

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('active');
      }
    });
  }, observerOptions);

  // Observe all elements with class 'reveal'
  // We use a slight timeout to ensure DOM is rendered, though in Vue mounted it should be fine.
  // However, child components might take a tick to render.
  setTimeout(() => {
    document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
  }, 100);
});
</script>

<template>
  <TheHeader />
  <main>
    <TheHero />
    <TheFeatures />
    <TheMobileOffice />
    <TheStats />
  </main>
  <TheFooter />
</template>

<style>
/* Import global styles */
@import './assets/base.css';
</style>
