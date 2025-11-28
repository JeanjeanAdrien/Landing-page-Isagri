# ISAGRI Landing Page

Ce projet est une application **Vue.js 3** moderne utilisant **Vite**.

## 🚀 Fonctionnalités

*   **Architecture Modulaire** : Découpage en composants Vue réutilisables (`TheHeader`, `TheHero`, `TheFeatures`, etc.).
*   **Performance** : Utilisation de Vite pour un développement rapide et des builds optimisés.
*   **Animations** :
    *   *Scroll Reveal* : Apparition fluide des éléments au défilement.
    *   *Compteurs Animés* : Les statistiques s'incrémentent dynamiquement.
    *   *Interactivité* : Section "Bureau Mobile" avec onglets interactifs.
*   **Styles** : CSS moderne avec variables globales et styles scopés par composant.
*   **Responsive** : Adapté aux mobiles, tablettes et desktops.

## 🛠️ Installation et Démarrage

Assurez-vous d'avoir [Node.js](https://nodejs.org/) installé.

1.  **Installer les dépendances**
    ```bash
    npm install
    ```

2.  **Lancer le serveur de développement**
    ```bash
    npm run dev
    ```
    L'application sera accessible à l'adresse `http://localhost:5173`.

3.  **Construire pour la production**
    ```bash
    npm run build
    ```

## 📂 Structure du Projet

```
isagri-vue/
├── public/              # Fichiers statiques
├── src/
│   ├── assets/          # Styles globaux (base.css) et images
│   ├── components/      # Composants Vue
│   │   ├── TheHeader.vue
│   │   ├── TheHero.vue
│   │   ├── TheFeatures.vue
│   │   ├── TheMobileOffice.vue
│   │   ├── TheStats.vue
│   │   └── TheFooter.vue
│   ├── App.vue          # Composant racine
│   └── main.ts          # Point d'entrée
├── index.html           # Fichier HTML principal
├── package.json         # Dépendances et scripts
└── vite.config.ts       # Configuration Vite
```

## 🎨 Design

Le design respecte l'identité visuelle ISAGRI :
*   **Couleurs** : Vert ISAGRI (`#8CC63F`), Blanc, Gris foncé.
*   **Typographie** : Police `Inter` pour une lisibilité optimale.
*   **Icônes** : FontAwesome.

