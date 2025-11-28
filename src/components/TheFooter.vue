<template>
  <footer>
    <div class="container">
      <div class="footer-content">
        <div class="footer-col">
          <h4>ISAGRI</h4>
          <p style="color:#a0aeb9; font-size:0.9rem;">Le partenaire informatique de l'agriculture française et européenne.</p>
        </div>
        <div class="footer-col">
          <h4>Produits</h4>
          <ul>
            <li>Geofolia</li>
            <li>Isalait</li>
            <li>IsaVigne</li>
            <li>IsaCompta</li>
          </ul>
        </div>
        <div class="footer-col">
          <h4>Support</h4>
          <ul>
            <li>Assistance technique</li>
            <li>Formation</li>
            <li>Espace Client</li>
          </ul>
        </div>
        <div class="footer-col">
          <h4>Contact</h4>
          <button class="btn-primary" style="padding: 10px 20px; font-size: 0.9rem;">Nous appeler</button>
        </div>
      </div>
      <div class="footer-bottom">
        &copy; 2025 Groupe ISAGRI. Tous droits réservés. Mentions légales.
      </div>
    </div>
  </footer>
</template>

<style scoped>
footer {
  background: #2C3E50;
  color: white;
  padding: 60px 0 20px;
}

.footer-content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 40px;
  margin-bottom: 40px;
}

.footer-col h4 { margin-bottom: 20px; color: white; }
.footer-col ul li { margin-bottom: 10px; color: #a0aeb9; font-size: 0.9rem; cursor: pointer; }
.footer-col ul li:hover { color: var(--isagri-green); }

.footer-bottom {
  text-align: center;
  border-top: 1px solid rgba(255,255,255,0.1);
  padding-top: 20px;
  color: #6c7a89;
  font-size: 0.85rem;
}
</style>
