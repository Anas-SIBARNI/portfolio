# Portfolio Personnel - Anas Sibarni

Bienvenue sur le dépôt de mon portfolio personnel. Ce projet a été développé pour présenter mon profil, mes compétences et mes réalisations. C'est une application "Single Page Application" (SPA) conçue avec **Vue.js 3** et **TypeScript**.

**➡️ Site en ligne : [anas-sibarni.xyz](https://anas-sibarni.xyz)**

## ✅ Fonctionnalités

* **Design Responsive :** Entièrement conçu avec une approche **Mobile-First**.
* **Double Thème :** Un sélecteur de thème dynamique : basculer entre un mode **Clair** (vert) et un mode **Sombre**.
* **Composants Dynamiques :** Chaque section (Accueil, Projets, Compétences...) est un composant Vue distinct.
* **Interactivité :**
    - Formulaire de contact fonctionnel (Formspree).
    - Bouton "Copier Email" avec animation de confirmation.
    - Barre de navigation avec effet "verre teinté en blanc", menu hamburger sur mobile.
    - Animations CSS (cadre photo, survol des liens, etc.).

## 🛠️ Stack Technique

* **Front-End :**
    * [Vue.js 3](https://vuejs.org/) (API Composition)
    * [TypeScript](https://www.typescriptlang.org/)
    * [Vite](https://vitejs.dev/) (Outil de build et serveur de développement)
* **Déploiement :**
    * Serveur : **VPS** (Ubuntu)
    * Serveur Web : **Nginx**
    * SSL : **Let's Encrypt**
    * Script de déploiement : `rsync` via SSH

## ⌨️ Installation et Lancement en local
  
Ce projet utilise [Node.js](https://nodejs.org/) et [npm](https://www.npmjs.com/).

1.  **Clonez le dépôt :**
    ```bash
    git clone https://github.com/Anas-SIBARNI/portfolio.git
    cd portfolio
    ```

2.  **Installez les dépendances :**
    ```bash
    npm install
    ```

3.  **Lancez le serveur de développement :**
    ```bash
    npm run dev
    ```
    Si votre port `5173` n'est déjà occupé par un autre programmee, mon site est normalement accessible sur `http://localhost:5173` !

## 📦 Déploiement : mise en production

Un script npm personnalisé a été configuré pour automatiser le déploiement sur mon VPS. (c'est privé)

```bash
npm run deploy
```
