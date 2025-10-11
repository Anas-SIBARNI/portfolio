<script setup lang="ts">
import Accueil from './components/Accueil.vue';
import APropos from './components/APropos.vue'
import Realisations from './components/Realisations.vue'

const projets = [{ id: 1, titre: 'Mon premier projet' },{ id: 2, titre: 'Mon deuxième projet' }]

</script>

<template>
  <div class="boules"></div>
  <main>
    <Accueil />
    <Competences />
    <Formation />
    <Realisations />
    <Contact />
  </main>
</template>
<style>

main {
  max-width: 800px;
  margin: 0 auto;
}

</style>
