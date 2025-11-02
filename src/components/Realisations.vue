<script setup lang="ts">
defineProps<{
  projets: {
    id: number;
    titre: string;
    description: string;
    outils: string[];
    image: string | null;
    githubUrl: string;
  }[]
}>()
</script>

<template>
  <section class="realisations-section">
    <h2>Réalisations</h2>
    <div class="projets-grille">
      
      <a 
        v-for="projet in projets" 
        :key="projet.id" 
        :href="projet.githubUrl"
        target="_blank" 
        rel="noopener noreferrer"
        class="projet-block"
      >
        
        <img 
          v-if="projet.image" 
          :src="projet.image" 
          :alt="`Aperçu du projet ${projet.titre}`" 
          class="projet-image"
        />

        <div class="projet-contenu">
          <h3 class="projet-titre">{{ projet.titre }}</h3>
          <p class="projet-description">{{ projet.description }}</p>
          <ul class="outils-liste">
            <li v-for="tech in projet.outils" :key="tech" class="outils-tag">
              {{ tech }}
            </li>
          </ul>
        </div>
      </a> </div>
  </section>
</template>

<style scoped>
.realisations-section {
  padding: 2rem 0;
}

.projets-grille {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1.5rem;
}

.projet-block {
  background-color: var(--couleur-surface-fond);
  border-radius: 15px;
  border: 1px solid var(--couleur-surface-bordure);
  transition: all 0.3s ease;
  display: flex;
  flex-direction: column;
  overflow: hidden;

  /* enlever l'apparence de lien par défaut */
  text-decoration: none;
  color: var(--couleur-texte); 
}

.projet-block:hover {
  transform: translateY(-5px);
  border-color: var(--couleur-accent-action);
}

.projet-image {
  width: 100%;
  aspect-ratio: 16 / 9;
  object-fit: cover;
  border-bottom: 1px solid var(--couleur-surface-bordure);
}

.projet-contenu {
  padding: 1.5rem;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
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

.outils-liste {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.outils-tag {
  background-color: var(--couleur-tag-fond);
  padding: 0.3rem 0.7rem;
  border-radius: 999px;
  font-size: 0.8rem;
  font-weight: 500;
}

@media (min-width: 769px) {
  .projets-grille {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>