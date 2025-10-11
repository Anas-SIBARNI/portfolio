<script setup lang="ts">
// Pour l'instant, nous n'avons pas besoin de code TypeScript ici.
// Ce composant est purement visuel.
</script>

<template>
  <section class="accueil-section">
    <div class="contenu">
      <h1 class="nom">Anas Sibarni</h1>
      <p class="sous-titre">Étudiant en Informatique - Conception d'Application</p>
      <p class="accroche">
        En 2ème année de BUT Informatique, je suis à la recherche d'un stage de 8 à 10 semaines à partir d'avril 2026 et d'une alternance pour ma 3ème année.
      </p>
      <div class="liens-sociaux">
        <a href="https://github.com/Anas-SIBARNI" target="_blank">GitHub</a>
        <a href="https://www.linkedin.com/in/anas-sibarni/" target="_blank">LinkedIn</a>
      </div>
    </div>
  </section>
</template>

<style scoped>
/* =================================== */
/* Styles de base (Mobile First)       */
/* =================================== */
.accueil-section {
  /* Sur mobile, on veut que la section prenne toute la hauteur de l'écran */
  min-height: 90vh; 
  display: flex;
  flex-direction: column; /* Les éléments s'empilent verticalement */
  justify-content: center; /* Centrage vertical */
  align-items: center; /* Centrage horizontal */
  text-align: center;
  padding: 1rem;
}

.nom {
  font-size: 2.8rem; /* Taille adaptée au mobile */
  font-weight: 700;
  margin-bottom: 0.5rem;
}

.sous-titre {
  font-size: 1.1rem;
  color: var(--couleur-texte-secondaire);
  margin-bottom: 1.5rem;
  font-weight: 600;
}

.accroche {
  max-width: 500px;
  margin-bottom: 2rem;
  color: var(--couleur-texte-secondaire);
}

.liens-sociaux a {
  margin: 0 0.5rem;
  padding: 0.8rem 1rem;
  border-radius: 12px;
  font-weight: 600;
  text-decoration: none;
  transition: .25s ease;
  border: 1px solid rgba(255, 255, 255, 0.25);
  background: rgba(255, 255, 255, 0.05);
  color: var(--couleur-texte);
}

.liens-sociaux a:hover {
  border-color: var(--couleur-texte);
  background: rgba(255, 255, 255, 0.12);
}

/* =================================== */
/* Styles pour écrans plus grands (Desktop) */
/* Ce code ne s'appliquera que si la largeur de l'écran est de 768px ou plus */
/* =================================== */
@media (min-width: 768px) {
  .nom {
    font-size: 4rem; /* On augmente la taille du titre sur grand écran */
  }

  .sous-titre {
    font-size: 1.5rem;
  }
}
</style>