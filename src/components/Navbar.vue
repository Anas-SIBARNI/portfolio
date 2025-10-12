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
/* --- Style de la barre "Pilule" --- */
.navbar {
  position: fixed;
  top: 1.5rem;
  left: 50%;
  transform: translateX(-50%);
  z-index: 100;
  
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.25);
  border-radius: 999px;
  box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.2);
  padding: 0.5rem;
}

.menu-hamburger {
  display: block; /* Visible sur mobile */
  font-size: 1.5rem;
  background: none;
  border: none;
  color: var(--couleur-texte);
  cursor: pointer;
  padding: 0.2rem 0.5rem;
}


/* --- Style du panneau de liens (par défaut, caché en haut) --- */
.nav-links {
  /* Position et état initial (caché) */
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  transform: translateY(-100%); /* Caché au-dessus de l'écran */
  opacity: 0;
  visibility: hidden;
  transition: transform 0.4s ease-in-out, opacity 0.4s ease-in-out;
  /* Style du panneau */
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 2rem;
  background: rgba(11, 16, 32, 0.95);
  backdrop-filter: blur(5px);
  list-style: none;
  padding: 0;
  margin: 0;
  z-index: 99;
}

/* --- Style quand le menu est ouvert --- */
.nav-links.est-ouvert {
  transform: translateY(0); /* On le fait glisser à sa position normale */
  opacity: 1;
  visibility: visible;
}

.nav-links.est-ouvert a {
  font-size: 1.8rem;
  color: var(--couleur-texte);
  text-decoration: none;
}

.nav-links a::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: 0.5rem; /* Ajustez pour la position verticale */
  height: 2px;
  background-color: var(--couleur-texte);
  width: 100%; /* La ligne fait toute la largeur du lien */
  
  transform: scaleX(0); /* Par défaut, la ligne est "écrasée", donc invisible */
  transform-origin: left; /* L'animation partira de la gauche */
  transition: transform 0.3s ease-in-out; /* L'animation ! */
}


/* --- Styles pour écrans plus grands (Desktop) --- */
@media (min-width: 769px) {
  .navbar {
    background: none;
    backdrop-filter: none;
    border: none;
    box-shadow: none;
  }
  
  /* On cache le bouton hamburger */
  .menu-hamburger {
    display: none;
  }
  
  /* Et on applique le style de la pilule directement à la liste de liens */
  .nav-links {
    /* On annule le style du panneau mobile */
    position: static;
    transform: none;
    opacity: 1;
    visibility: visible;
    flex-direction: row;
    height: auto;
    width: auto;
    
    /* On applique le style de la pilule ici */
    background: rgba(255, 255, 255, 0.2);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 255, 255, 0.25);
    border-radius: 999px;
    box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.2);
    padding: 0.5rem;
    gap: 0.5rem;
    list-style: none;
    position: fixed;
    top: 1.5rem;
    left: 50%;
    transform: translateX(-50%);
    z-index: 100;
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