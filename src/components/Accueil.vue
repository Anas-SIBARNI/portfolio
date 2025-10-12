<script setup lang="ts">
import { ref } from 'vue';

// Variable pour suivre l'état de la copie
const estCopie = ref(false);

// Fonction asynchrone pour copier l'email
async function copierEmail() {
  // Empêche de re-cliquer pendant l'animation
  if (estCopie.value) return;

  try {
    await navigator.clipboard.writeText('anas.sibarni@gmail.com');
    estCopie.value = true; // On passe à l'état "copié"

    // Après 2 secondes, on revient à l'état initial
    setTimeout(() => {
      estCopie.value = false;
    }, 2000);
  } catch (err) {
    console.error('Erreur lors de la copie du mail : ', err);
  }
}
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
        <a href="https://github.com/Anas-SIBARNI" target="_blank" class="lien">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path></svg>
          <span>GitHub</span>
        </a>

        <a href="https://www.linkedin.com/in/anas-sibarni/" target="_blank" class="lien">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect x="2" y="9" width="4" height="12"></rect><circle cx="4" cy="4" r="2"></circle></svg>
          <span>LinkedIn</span>
        </a>

        <button @click="copierEmail" class="lien">
          <div class="icone-container">
            <svg :class="{ 'icone-active': !estCopie }" class="icone" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline></svg>
            <svg :class="{ 'icone-active': estCopie }" class="icone" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>
          </div>
          <span>{{ estCopie ? 'Copié !' : 'Email' }}</span>
        </button>
      </div>
    </div>
  </section>
</template>
<style scoped>
/* =================================== */
/* Styles de base (Mobile First)       */
/* =================================== */
.accueil-section {
  min-height: 90vh; 
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 1rem;
}

.nom {
  font-size: 2.8rem;
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

.liens-sociaux {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1rem;
}

/* Style unifié qui utilise les variables de thème */
.lien {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  padding: 0.8rem 1.2rem;
  border-radius: 12px;
  font-weight: 600;
  text-decoration: none;
  transition: .25s ease;
  border: 1px solid var(--couleur-surface-bordure); /* Utilisation de la variable */
  background: var(--couleur-surface-fond);      /* Utilisation de la variable */
  color: var(--couleur-texte);
  font-family: inherit;
  font-size: 1rem;
  cursor: pointer;
}

.lien:hover {
  border-color: var(--couleur-accent-action); /* Utilisation de la variable */
  background: transparent; /* On rend le fond transparent pour un effet plus subtil */
}

.lien svg {
  width: 20px;
  height: 20px;
  stroke: var(--couleur-texte); /* On s'assure que les icônes suivent la couleur du texte */
}

/* --- Animation du bouton copier --- */
.icone-container {
  position: relative;
  width: 20px;
  height: 20px;
}
.icone {
  position: absolute;
  top: 0px;
  left: 0px;
  transition: transform 0.3s ease-out, opacity 0.3s ease-out;
}
.icone.icone-active {
  transform: scale(1);
  opacity: 1;
}
.icone:not(.icone-active) {
  transform: scale(0);
  opacity: 0;
}


/* =================================== */
/* Styles pour écrans plus grands (Desktop) */
/* =================================== */
@media (min-width: 768px) {
  .nom {
    font-size: 4rem;
  }

  .sous-titre {
    font-size: 1.5rem;
  }
}
</style>