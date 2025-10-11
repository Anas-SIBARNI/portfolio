<script setup lang="ts">
defineProps(['formations'])
</script>
<template>
    <section class="formation-section">
      <h2>Formation</h2>
      
      <div v-for="formation in formations" :key="formation.id" class="formation-item">
        <div class="formation-header">
          <h3 class="titre">{{ formation.titre }}</h3>
          <span class="annee">{{ formation.annee }}</span>
        </div>
        <p class="etablissement">{{ formation.etablissement }}</p>
      </div>
    </section>
  </template>


<style scoped>
/* =================================== */
/* Styles de base (Mobile First)       */
/* =================================== */
.formation-item {
  background-color: rgba(39, 39, 42, 0.7);
  padding: 1.5rem;
  border-radius: 10px;
  border-left: 3px solid var(--couleur-accent); /* Ligne de style sur le côté */
  margin-bottom: 1.5rem;
}

.formation-header {
  display: flex;
  flex-wrap: wrap; 
  justify-content: space-between;
  align-items: baseline;
  gap: 1rem; /* Espace entre le titre et l'année */
  margin-bottom: 0.5rem;
}

.titre {
  font-size: 1.2rem;
  font-weight: 600;
  color: var(--couleur-texte);
  margin: 0; /* On enlève la marge par défaut du h3 */
}

.annee {
  font-size: 0.9rem;
  color: var(--couleur-texte-secondaire);
  font-style: italic;
  flex-shrink: 0;
}

.etablissement {
  font-size: 1rem;
  color: var(--couleur-texte-secondaire);
  margin: 0;
}

/* =================================== */
/* Styles pour écrans plus grands (Desktop) */
/* =================================== */
@media (min-width: 768px) {
  .formation-item {
    transition: all 0.3s ease;
  }
  .formation-item:hover {
    transform: translateY(-5px);
    background-color: rgba(50, 50, 50, 0.9);
  }
}
</style>
