<template>
  <section class="features">
    <div class="container">
      <div class="section-header reveal">
        <h2>Un écosystème pour <span class="text-green">chaque métier</span></h2>
        <p style="color:var(--text-light)">Des solutions adaptées à la réalité de votre terrain.</p>
      </div>

      <div class="grid-cards">
        <!-- Card 1 -->
        <div class="smart-card reveal">
          <i class="fas fa-tractor"></i>
          <h3>Grandes Cultures</h3>
          <p>Optimisez vos intrants, suivez vos parcelles et sécurisez vos marges avec Geofolia.</p>
        </div>
        <!-- Card 2 -->
        <div class="smart-card reveal">
          <i class="fas fa-cow"></i>
          <h3>Élevage</h3>
          <p>Suivi de troupeau, génétique et contrôle laitier au bout des doigts.</p>
        </div>
        <!-- Card 3 -->
        <div class="smart-card reveal">
          <i class="fas fa-wine-glass-alt"></i>
          <h3>Viticulture</h3>
          <p>De la vigne à la bouteille : traçabilité, gestion commerciale et douanes.</p>
        </div>
        <!-- Card 4 -->
        <div class="smart-card reveal">
          <i class="fas fa-calculator"></i>
          <h3>Comptabilité</h3>
          <p>Gagnez du temps administratif. Une gestion simplifiée, connectée à votre banque.</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.features {
  padding: 100px 0;
  background: var(--bg-white);
}

.section-header {
  text-align: center;
  margin-bottom: 60px;
}

.section-header h2 {
  font-size: 2.5rem;
  margin-bottom: 15px;
}

.grid-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 30px;
}

.smart-card {
  background: white;
  padding: 40px 30px;
  border-radius: var(--radius-card);
  border: 1px solid #eee;
  transition: all 0.4s cubic-bezier(0.25, 0.8, 0.25, 1);
  cursor: pointer;
  position: relative;
  overflow: hidden;
}

.smart-card:hover {
  transform: translateY(-8px);
  box-shadow: var(--shadow-soft);
  border-color: transparent;
}

.smart-card i {
  font-size: 2rem;
  color: #ccc;
  margin-bottom: 20px;
  transition: color 0.3s;
}

.smart-card:hover i { color: var(--isagri-green); }

.smart-card h3 { font-size: 1.25rem; margin-bottom: 10px; }
.smart-card p { color: var(--text-light); font-size: 0.95rem; }
</style>
