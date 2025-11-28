<template>
  <section class="hero">
    <div class="shape shape-1"></div>
    <div class="shape shape-2"></div>
    
    <div class="container hero-content">
      <div class="hero-text reveal">
        <h1>L'agriculture connectée,<br><span class="text-green">simplement.</span></h1>
        <p>Gérez votre exploitation avec une clarté absolue. Logiciels, comptabilité et météo, centralisés pour libérer votre esprit.</p>
        <div style="display: flex; gap: 15px; flex-wrap: wrap;">
          <button class="btn-primary">Découvrir les outils</button>
          <button style="background:transparent; border: 2px solid #eee; padding: 12px 28px; border-radius: 50px; font-weight:600; cursor:pointer;">Voir la démo</button>
        </div>
      </div>

      <div class="hero-visual">
        <div class="glass-card">
          <div class="stat-row">
            <div class="icon-box"><i class="fas fa-sun"></i></div>
            <div>
              <div style="font-weight: 700; font-size: 1.1rem;">Météo Parfaite</div>
              <div style="color: #888; font-size: 0.9rem;">Semis optimal J+2</div>
            </div>
          </div>
          <div class="stat-row">
            <div class="icon-box"><i class="fas fa-chart-line"></i></div>
            <div>
              <div style="font-weight: 700; font-size: 1.1rem;">Marge Brute</div>
              <div style="color: var(--isagri-green); font-weight: 600;">+12% vs N-1</div>
            </div>
          </div>
          <div class="stat-row">
            <div class="icon-box"><i class="fas fa-check-circle"></i></div>
            <div>
              <div style="font-weight: 700; font-size: 1.1rem;">Déclaration PAC</div>
              <div style="color: #888; font-size: 0.9rem;">Validée et envoyée</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  padding-top: 140px;
  padding-bottom: 80px;
  min-height: 90vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  background: radial-gradient(circle at top right, #f4faeb 0%, #ffffff 60%);
}

.hero-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 50px;
}

.hero-text {
  flex: 1;
  z-index: 2;
}

.hero h1 {
  font-size: 3.5rem;
  line-height: 1.1;
  margin-bottom: 20px;
  letter-spacing: -1px;
}

.hero p {
  font-size: 1.2rem;
  color: var(--text-light);
  margin-bottom: 35px;
  max-width: 500px;
}

/* Abstract CSS Visuals */
.hero-visual {
  flex: 1;
  height: 500px;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.shape {
  position: absolute;
  border-radius: 50%;
  filter: blur(40px);
  opacity: 0.6;
  animation: float 6s ease-in-out infinite;
}

.shape-1 {
  width: 300px;
  height: 300px;
  background: #d4edb4;
  top: 10%;
  right: 10%;
}

.shape-2 {
  width: 200px;
  height: 200px;
  background: #8CC63F;
  bottom: 20%;
  left: 20%;
  animation-delay: 1s;
}

.glass-card {
  position: relative;
  width: 380px;
  background: rgba(255, 255, 255, 0.7);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.8);
  padding: 30px;
  border-radius: 24px;
  box-shadow: var(--shadow-soft);
  z-index: 10;
  animation: slideUp 1s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;
}

.stat-row {
  display: flex;
  align-items: center;
  gap: 15px;
  margin-bottom: 20px;
  padding-bottom: 20px;
  border-bottom: 1px solid rgba(0,0,0,0.05);
}
.stat-row:last-child { border-bottom: none; margin-bottom: 0; padding-bottom: 0; }

.icon-box {
  width: 50px;
  height: 50px;
  background: #f0f7e6;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--isagri-green);
  font-size: 1.2rem;
}

@media (max-width: 900px) {
  .hero-content { flex-direction: column; text-align: center; }
  .hero-visual { width: 100%; height: 350px; }
  .hero h1 { font-size: 2.5rem; }
  .hero p { margin: 0 auto 30px; }
}
</style>
