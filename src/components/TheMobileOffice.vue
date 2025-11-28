<template>
  <section class="mobile-office">
    <div class="container demo-layout">
      <div class="demo-text reveal">
        <h2>Votre bureau,<br>partout avec vous.</h2>
        <p style="color: var(--text-light); margin-bottom: 20px;">L'application ISAGRI s'adapte à votre smartphone ou tablette. Saisissez vos interventions directement depuis la cabine.</p>
        
        <ul class="demo-list">
          <li :class="{ active: activeTab === 0 }" @click="activeTab = 0">
            <i class="fas fa-tachometer-alt"></i> Tableau de bord
          </li>
          <li :class="{ active: activeTab === 1 }" @click="activeTab = 1">
            <i class="fas fa-cloud-sun"></i> Météo de précision
          </li>
          <li :class="{ active: activeTab === 2 }" @click="activeTab = 2">
            <i class="fas fa-euro-sign"></i> Rentabilité temps réel
          </li>
        </ul>
      </div>

      <div class="tablet-mockup reveal">
        <div class="tablet-screen">
          <div class="t-sidebar">
            <div class="t-icon active"><i class="fas fa-home"></i></div>
            <div class="t-icon"><i class="fas fa-layer-group"></i></div>
            <div class="t-icon"><i class="fas fa-cog"></i></div>
          </div>
          <div class="t-content" :key="activeTab">
            <!-- Dashboard Content -->
            <template v-if="activeTab === 0">
              <div class="t-header">
                <h3>Vue d'ensemble</h3>
                <span class="status-badge">En ligne</span>
              </div>
              <div class="t-card">
                <div class="card-label">Alertes</div>
                <div class="card-value">Aucune anomalie</div>
              </div>
              <div class="t-card flex-1">
                <div class="card-label">Trésorerie</div>
                <div class="bar-chart">
                  <div class="bar" style="height:40%"></div>
                  <div class="bar" style="height:60%"></div>
                  <div class="bar fill" style="height:85%"></div>
                  <div class="bar" style="height:55%"></div>
                  <div class="bar" style="height:70%"></div>
                </div>
              </div>
            </template>

            <!-- Weather Content -->
            <template v-if="activeTab === 1">
              <div class="t-header">
                <h3>Météo Locale</h3>
                <i class="fas fa-sun" style="color:#f39c12"></i>
              </div>
              <div class="t-card">
                <div style="font-size:2rem;font-weight:700">22°C</div>
                <div style="color:#888;">Vent: 15km/h NO</div>
              </div>
              <div class="t-card flex-1">
                <div class="card-label" style="margin-bottom:10px;">Prévisions Pluie</div>
                <div class="weather-bars">
                   <div style="width:20%;background:#8CC63F;height:20%;border-radius:4px;"></div>
                   <div style="width:20%;background:#eee;height:10%;border-radius:4px;"></div>
                   <div style="width:20%;background:#eee;height:10%;border-radius:4px;"></div>
                   <div style="width:20%;background:#8CC63F;height:60%;border-radius:4px;"></div>
                </div>
              </div>
            </template>

            <!-- Profitability Content -->
            <template v-if="activeTab === 2">
              <div class="t-header">
                <h3>Marge Brute</h3>
                <span style="color:#8CC63F">+4.5%</span>
              </div>
              <div class="t-card flex-1 column-center">
                <div class="profit-row"><span>Blé Tendre</span><b>185€/t</b></div>
                <div class="progress-bg"><div class="progress-fill" style="width:80%"></div></div>
                <br>
                <div class="profit-row"><span>Maïs</span><b>160€/t</b></div>
                <div class="progress-bg"><div class="progress-fill" style="width:65%"></div></div>
              </div>
            </template>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';

const activeTab = ref(0);
</script>

<style scoped>
.mobile-office {
  padding: 100px 0;
  background: linear-gradient(to bottom, #ffffff, #f8f9fa);
}

.demo-layout {
  display: flex;
  align-items: center;
  gap: 60px;
}

.demo-text { flex: 1; }
.demo-text h2 { font-size: 2.5rem; margin-bottom: 20px; }
.demo-list { margin: 30px 0; }
.demo-list li {
  display: flex;
  align-items: center;
  gap: 15px;
  margin-bottom: 15px;
  font-size: 1.1rem;
  color: var(--text-light);
  cursor: pointer;
  padding: 10px;
  border-radius: 8px;
  transition: 0.2s;
}
.demo-list li:hover, .demo-list li.active {
  background: white;
  box-shadow: 0 2px 10px rgba(0,0,0,0.05);
  color: var(--isagri-green);
  font-weight: 500;
}

.tablet-mockup {
  flex: 1.2;
  background: #1a1a1a;
  padding: 15px;
  border-radius: 30px;
  box-shadow: 0 30px 60px -15px rgba(0,0,0,0.2);
  position: relative;
}

.tablet-screen {
  background: #f4f6f8;
  border-radius: 20px;
  overflow: hidden;
  height: 400px;
  display: flex;
}

.t-sidebar {
  width: 70px;
  background: white;
  border-right: 1px solid #eee;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-top: 20px;
  gap: 20px;
}
.t-icon { width: 40px; height: 40px; border-radius: 10px; display: grid; place-items: center; color: #999; }
.t-icon.active { background: #efffd6; color: var(--isagri-green); }

.t-content { 
  flex: 1; 
  padding: 25px; 
  display: flex; 
  flex-direction: column; 
  gap: 20px; 
  animation: fadeIn 0.3s ease-out;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(5px); }
  to { opacity: 1; transform: translateY(0); }
}

.t-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px; }
.t-card { background: white; padding: 20px; border-radius: 12px; box-shadow: 0 2px 5px rgba(0,0,0,0.03); }

.status-badge { font-size: 0.8rem; background: #eee; padding: 4px 8px; border-radius: 4px; }
.card-label { font-size:0.9rem; color:#888; }
.card-value { font-weight:700; font-size:1.2rem; }
.flex-1 { flex: 1; }

.bar-chart { display: flex; align-items: flex-end; gap: 10px; height: 100px; margin-top: 15px; }
.bar { width: 100%; background: #eee; border-radius: 4px 4px 0 0; transition: height 1s ease; height: 0; }
.bar.fill { background: var(--isagri-green); }

.weather-bars { display:flex; gap:5px; height:100px; align-items:flex-end; }
.column-center { display:flex; flex-direction:column; justify-content:center; }
.profit-row { display:flex; justify-content:space-between; margin-bottom:10px; }
.progress-bg { width:100%; height:8px; background:#eee; border-radius:4px; }
.progress-fill { height:100%; background:#8CC63F; border-radius:4px; }

@media (max-width: 900px) {
  .demo-layout { flex-direction: column; }
  .tablet-mockup { width: 100%; }
}
</style>
