<script setup lang="ts">
defineProps<{
  competences: {
    [key: string]: { nom: string; logo: string | null }[]
  }
}>()

function formatCategorie(categorieName: string | number): string {
  if (typeof categorieName !== 'string') {
    return String(categorieName);
  }

  switch (categorieName) {
    case 'baseDeDonnees':
      return 'Base de données';
    case 'deploiement':
      return 'Déploiement';
    case 'langages':
      return 'Langages';
    case 'depots':
      return 'Dépôts';
    default:
      // Retourne le nom original s'il n'est pas dans la liste
      return categorieName;
  }
}
</script>

<template>
  <section class="competences-section">
    <h2>Compétences</h2>
    <div v-for="(liste, categorie) in competences" :key="categorie" class="categorie">
      
      <h3>{{ formatCategorie(categorie) }}</h3>

      <div class="container">
        <div v-for="comp in liste" :key="comp.nom" class="block">
          <img v-if="comp.logo" :src="comp.logo" :alt="`Logo ${comp.nom}`" />
          <span>{{ comp.nom }}</span>
        </div>
      </div>
    </div>
  </section>
</template>
<style scoped>
.competences-section {
  padding: 2rem 0;
}

.categorie {
  margin-bottom: 2.5rem;
}

.categorie h3 {
  text-transform: capitalize;
  font-size: 1.2rem;
  color: var(--couleur-texte-secondaire);
  margin-bottom: 1.5rem;
  text-align: center;
}

.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1rem;
}

.block {
  background-color: var(--couleur-surface-fond);
  border: 1px solid var(--couleur-surface-bordure);
  border-radius: 10px;
  /* MODIFIÉ : Le padding est presque nul, sauf à droite pour le texte */
  padding: 0 30px 0 0;
  font-weight: 500;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  /* MODIFIÉ : Le gap est supprimé car la marge de l'image s'en charge */
  gap: 0;
}

.block:hover {
  transform: translateY(-5px);
  background-color: var(--couleur-surface-survol-fond);
  border-color: var(--couleur-surface-survol-bordure);
}

.block img {
  height: 30px;
  width: 30px;
  /* CONSERVÉ : Votre marge de 30px */
  margin: 30px;
}
</style>