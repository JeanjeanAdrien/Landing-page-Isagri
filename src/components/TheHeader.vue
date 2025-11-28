<template>
  <header>
    <div class="container nav-container">
      <div class="logo">ISAGRI<span>.</span></div>
      <nav class="desktop-nav">
        <ul>
          <li><a href="#">Solutions</a></li>
          <li><a href="#">Témoignages</a></li>
          <li><a href="#">Groupe</a></li>
          <li><a href="#">Contact</a></li>
        </ul>
      </nav>
      <button class="btn-primary" style="padding: 10px 20px; font-size: 0.9rem;">Espace Client</button>
    </div>
  </header>
</template>

<style scoped>
header {
  padding: 20px 0;
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 1000;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  box-shadow: 0 1px 0 rgba(0,0,0,0.05);
}

.nav-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-size: 24px;
  font-weight: 800;
  color: var(--text-dark);
  letter-spacing: -0.5px;
}

.logo span { color: var(--isagri-green); }

nav ul { display: flex; gap: 30px; }
nav a { font-weight: 500; font-size: 0.95rem; color: var(--text-light); }
nav a:hover { color: var(--isagri-green); }
</style>
