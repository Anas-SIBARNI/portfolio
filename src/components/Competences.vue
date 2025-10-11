<script setup lang="ts">
defineProps<{
  competences: {
    [key: string]: string[]
  }
}>()
</script>

<template>
  <section class="competences-section">
    <h2>Compétences</h2>
    <div v-for="(listeCompetences, categorie) in competences" :key="categorie" class="categorie">

        <h3>{{ categorie }}</h3>

        <div v-for="comp in listeCompetences" class="block" :key="comp">
            {{ comp }}
        </div>

      

    </div>
  </section>
</template>

<style scoped>
.competences-section {
  padding: 2rem 0;
}

.categorie {
  margin-bottom: 2rem;
}

.categorie h3 {
  text-transform: capitalize; /* première lettre en majuscule */
  font-size: 1.2rem;
  color: var(--couleur-texte-secondaire);
  margin-bottom: 1rem;
  text-align: center;
}

.container {
  display: flex;
  flex-wrap: wrap; /*  passer à la ligne */
  justify-content: center;
  gap: 1rem; /* Espace entre les blocks */
}

.block {
  background-color: rgba(39, 39, 42, 0.7);
  padding: 0.8rem 1.2rem;
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 10px;
  transition: all 0.3s ease;
  font-weight: 500;
}

.block:hover {
  transform: translateY(-5px); 
  background-color: rgba(50, 50, 50, 0.9);
  border-color: rgba(255, 255, 255, 0.2);
}
</style>