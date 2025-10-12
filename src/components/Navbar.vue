<script setup lang="ts">
import { ref } from 'vue';

const menuOuvert = ref(false);
</script>

<template>
  <nav class="navbar" :class="{ 'est-ouvert': menuOuvert }">
      <button class="menu-hamburger" @click="menuOuvert = !menuOuvert">☰</button>
      <ul class="nav-links">
          <li><a href="#accueil" @click="menuOuvert = false">Accueil</a></li>
          <li><a href="#competences" @click="menuOuvert = false">Compétences</a></li>
          <li><a href="#formation" @click="menuOuvert = false">Formation</a></li>
          <li><a href="#realisations" @click="menuOuvert = false">Réalisations</a></li>
          <li><a href="#contact" @click="menuOuvert = false">Contact</a></li>
      </ul>
  </nav>
</template>
<style scoped>
/* --- Style de base de la barre (Mobile First) --- */
.navbar {
  /* Position */
  position: fixed;
  top: 1.5rem;
  left: 50%;
  transform: translateX(-50%);
  z-index: 100;
  box-sizing: border-box;

  /* Style Pilule */
  width: auto;
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.25);
  border-radius: 999px;
  box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.2);
  padding: 0.5rem;
  display: flex;
  align-items: center;
  transition: all 0.3s ease-in-out; /* Pour une transformation douce */
}

.menu-hamburger {
  display: block; /* Visible sur mobile */
  font-size: 1.5rem;
  background: none;
  border: none;
  color: var(--couleur-texte);
  cursor: pointer;
}

/* Par défaut sur mobile, les liens sont cachés */
.nav-links {
  display: none;
}

/* --- Style quand le menu est ouvert --- */
.navbar.est-ouvert {
  /* La pilule se transforme en panneau plein écran */
  top: 0;
  left: 0;
  transform: none;
  width: 100vw;
  height: 100vh;
  border-radius: 0;
  background: rgba(11, 16, 32, 0.95);
  flex-direction: column;
  justify-content: center;
}

.navbar.est-ouvert .nav-links {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;
  padding: 0;
  margin: 0;
  list-style: none;
}

.navbar.est-ouvert .nav-links a {
  font-size: 1.8rem;
  color: var(--couleur-texte);
  text-decoration: none;
}


/* --- Styles pour écrans plus grands (Desktop) --- */
@media (min-width: 769px) {
  /* On cache le bouton hamburger */
  .menu-hamburger {
    display: none;
  }
  
  /* On affiche les liens en ligne */
  .nav-links {
    display: flex;
    list-style: none;
    margin: 0;
    padding: 0;
    gap: 0.5rem;
  }
  
  .nav-links a {
    color: var(--couleur-texte);
    text-decoration: none;
    font-weight: 500;
    border-radius: 999px;
    transition: background-color 0.3s ease;
    padding: 0.75rem 1.2rem;
    font-size: 0.9rem;
  }

  .nav-links a:hover {
    background-color: rgba(255, 255, 255, 0.2);
  }
}
</style>