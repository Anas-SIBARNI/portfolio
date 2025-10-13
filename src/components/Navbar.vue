<script setup lang="ts">
import { ref } from 'vue';

const menuOuvert = ref(false);
</script>

<template>
  <nav class="navbar">
      <button class="menu-hamburger" @click="menuOuvert = !menuOuvert">☰</button>
  </nav>
  <ul class="nav-links" :class="{ 'est-ouvert': menuOuvert }">
      <li><a href="#accueil" @click="menuOuvert = false">Accueil</a></li>
      <li><a href="#competences" @click="menuOuvert = false">Compétences</a></li>
      <li><a href="#formation" @click="menuOuvert = false">Formation</a></li>
      <li><a href="#realisations" @click="menuOuvert = false">Réalisations</a></li>
      <li><a href="#contact" @click="menuOuvert = false">Contact</a></li>
  </ul>
</template>

<style scoped>
/* --- Style du conteneur de la barre --- */
.navbar {
  position: fixed;
  top: 1.5rem;
  right: 1.5rem;
  z-index: 100;
}

.menu-hamburger {
  display: block;
  font-size: 1.8rem;
  background: none;
  border: none;
  color: var(--couleur-texte);
  cursor: pointer;
  padding: 0.5rem;
  border-radius: 8px;
  transition: background-color 0.2s ease;
}

.menu-hamburger:hover {
  background-color: var(--couleur-surface-fond);
}


/* --- Style du panneau de liens (mobile) --- */
.nav-links {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  transform: translateY(-100%);
  opacity: 0;
  visibility: hidden;
  transition: transform 0.4s ease-in-out, opacity 0.4s ease-in-out;
  
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 2rem;
  background: var(--couleur-overlay-fond);
  backdrop-filter: blur(5px);
  list-style: none;
  padding: 0;
  margin: 0;
  z-index: 99;
}

.nav-links.est-ouvert {
  transform: translateY(0);
  opacity: 1;
  visibility: visible;
}

.nav-links.est-ouvert a {
  font-size: 1.8rem;
  color: var(--couleur-texte);
  text-decoration: none;
}


/* --- Styles pour écrans plus grands (Desktop) --- */
@media (min-width: 769px) {
  .navbar {
    /* Sur PC, la navbar est juste un conteneur vide pour le positionnement */
    background: none;
    backdrop-filter: none;
    border: none;
    box-shadow: none;
  }
  
  .menu-hamburger {
    display: none;
  }
  
  .nav-links {
    /* Réinitialisation pour le style "pilule" */
    position: fixed;
    top: 1.5rem;
    left: 50%;
    transform: translateX(-50%);
    opacity: 1;
    visibility: visible;
    flex-direction: row;
    height: auto;
    width: auto;
    
    /* Style de la pilule */
    background: var(--couleur-surface-fond);
    backdrop-filter: blur(10px);
    border: 1px solid var(--couleur-surface-bordure);
    border-radius: 999px;
    box-shadow: 0 8px 32px 0 var(--couleur-ombre);
    padding: 0.5rem;
    gap: 0.5rem;
  }
  
  .nav-links a {
    position: relative;
    padding: 0.5rem 0;
    margin: 0 1rem;
    color: var(--couleur-texte);
    text-decoration: none;
    font-weight: 500;
    font-size: 0.9rem;
    background-color: transparent;
  }

  .nav-links a:hover {
    background-color: transparent; /* Pas de changement de fond */
  }

  .nav-links a::after {
    content: '';
    position: absolute;
    width: 100%;
    height: 2px;
    background-color: var(--couleur-texte);
    bottom: 0;
    left: 0;
    transform: scaleX(0);
    transform-origin: bottom right;
    transition: transform 0.3s ease-out;
  }

  .nav-links a:hover::after {
    transform: scaleX(1);
    transform-origin: bottom left;
  }
}
</style>