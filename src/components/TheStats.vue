<template>
  <section class="stats" ref="statsSection">
    <div class="container stats-grid">
      <div class="stat-item">
        <h3>{{ displayUsers }}</h3>
        <p>Utilisateurs satisfaits</p>
      </div>
      <div class="stat-item">
        <h3>{{ displayYears }}</h3>
        <p>Ans d'expérience</p>
      </div>
      <div class="stat-item">
        <h3>{{ displayCountries }}</h3>
        <p>Pays couverts</p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const statsSection = ref(null);
const displayUsers = ref('0');
const displayYears = ref('0');
const displayCountries = ref('0');

const animateValue = (refValue, target, duration = 2000) => {
  let start = 0;
  const increment = target / (duration / 16);
  
  const update = () => {
    start += increment;
    if (start < target) {
      refValue.value = Math.ceil(start).toLocaleString('fr-FR');
      requestAnimationFrame(update);
    } else {
      refValue.value = target.toLocaleString('fr-FR') + (target > 1000 ? '+' : '');
    }
  };
  update();
};

onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    if (entries[0].isIntersecting) {
      animateValue(displayUsers, 150000);
      animateValue(displayYears, 40);
      animateValue(displayCountries, 12);
      observer.disconnect();
    }
  });
  
  if (statsSection.value) {
    observer.observe(statsSection.value);
  }
});
</script>

<style scoped>
.stats {
  padding: 80px 0;
  background: var(--bg-light);
  border-top: 1px solid #eee;
}

.stats-grid {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  gap: 40px;
  text-align: center;
}

.stat-item h3 {
  font-size: 3.5rem;
  color: var(--isagri-green);
  margin-bottom: 5px;
}

.stat-item p {
  font-size: 1.1rem;
  font-weight: 500;
  color: var(--text-dark);
}
</style>
