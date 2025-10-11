<script setup lang="ts">
import Accueil from './components/Accueil.vue';
import Competences from './components/Competences.vue';
import Formation from './components/Formation.vue';
import Realisations from './components/Realisations.vue';
import Contact from './components/Contact.vue';


const projets = [{ id: 1, titre: 'Mon premier projet' },{ id: 2, titre: 'Mon deuxième projet' }]
const competences = {
  langages: ['Java', 'Python', 'SQL', 'HTML/CSS', 'JavaScript'],
  backend: ['Node.js', 'Express', 'Socket.IO'],
  baseDeDonnees: ['PostgreSQL'],
  deploiement: ['Nginx', 'PM2', 'VPS OVH']
};



</script>

<template>
  <div class="boules"></div>
  <main>
    <Accueil />
    <Competences :competences="competences" />
    <Formation />
    <Realisations :projets="projets" />
    <Contact />
  </main>
</template>
<style>

main {
  max-width: 800px;
  margin: 0 auto;
}

</style>
