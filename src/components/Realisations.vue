<script setup lang="ts">
// On définit la structure attendue pour nos projets pour être plus précis
defineProps<{
  projets: {
    id: number;
    titre: string;
    description: string;
    technologies: string[];
  }[]
}>()
</script>

<template>
  <section class="realisations-section">
    <h2>Réalisations</h2>
    <div class="projets-grille">
      <div v-for="projet in projets" :key="projet.id" class="projet-carte">
        <h3 class="projet-titre">{{ projet.titre }}</h3>
        <p class="projet-description">{{ projet.description }}</p>
        <ul class="technologies-liste">
          <li v-for="tech in projet.technologies" :key="tech" class="tech-tag">
            {{ tech }}
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>
<style scoped>
/* =================================== */
/* Styles de base (Mobile First)       */
/* =================================== */
.realisations-section {
  padding: 2rem 0;
}

.projets-grille {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1.5rem;
}

.projet-carte {
  background-color: var(--couleur-surface-fond);
  padding: 1.5rem;
  border-radius: 15px;
  border: 1px solid var(--couleur-surface-bordure);
  display: flex;
  flex-direction: column;
  transition: all 0.3s ease;
}

.projet-carte:hover {
  transform: translateY(-5px);
  border-color: var(--couleur-accent-action);
}

.projet-titre {
  font-size: 1.3rem;
  font-weight: 600;
  margin: 0 0 1rem 0;
  color: var(--couleur-texte);
}

.projet-description {
  color: var(--couleur-texte-secondaire);
  flex-grow: 1;
  margin: 0 0 1.5rem 0;
}

.technologies-liste {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.tech-tag {
  background-color: var(--couleur-tag-fond);
  padding: 0.3rem 0.7rem;
  border-radius: 999px;
  font-size: 0.8rem;
  font-weight: 500;
}

/* =================================== */
/* Styles pour écrans plus grands (Desktop) */
/* =================================== */
@media (min-width: 769px) {
  .projets-grille {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>