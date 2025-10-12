<script setup lang="ts">
defineProps<{
  competences: {
    [key: string]: { nom: string; logo: string | null }[]
  }
}>()

function formatCategorie(categorieName: string | number): string {
  // contourner erreur categorie.replace(truc)
  if (typeof categorieName === 'string') {
    if(categorieName == "baseDeDonnees"){
      return categorieName.replace('baseDeDonnees', 'Base de données');
    } else if(categorieName == "deploiement"){
      return categorieName.replace('deploiement', 'Déploiement');
    } else if(categorieName == "langages"){
      return categorieName.replace('langages', 'Langages');
    } 
  }
  return String(categorieName);
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
  padding: 0.8rem 1.2rem;
  font-weight: 500;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.block:hover {
  transform: translateY(-5px);
  background-color: var(--couleur-surface-survol-fond);
  border-color: var(--couleur-surface-survol-bordure);
}

.block img {
  height: 24px;
  width: 24px;
}
</style>