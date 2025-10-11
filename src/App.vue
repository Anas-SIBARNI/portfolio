<script setup lang="ts">
import Navbar from './components/Navbar.vue';
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

const formations = [
  { 
    id: 1,
    annee: "2024 - Aujourd'hui",
    titre: "Bachelor Universitaire de Technologie - Informatique",
    etablissement: "Université de Lille - Villeneuve d'Ascq"
  },
  { 
    id: 2,
    annee: "Juillet 2024",
    titre: "Baccalauréat Général (Mention Bien)",
    etablissement: "Lycée Gustave Eiffel - Armentières"
  }
];

</script>

<template>
  <div class="boules"></div>
  <Navbar />
  <main>
    <Accueil id="accueil" />
    <Competences id="competences" :competences="competences" />
    <Formation id="formation" :formations="formations" />
    <Realisations id="realisations" :projets="projets" />
    <Contact id="contact" />
  </main>
</template>
<style>

main {
  max-width: 800px;
  margin: 0 auto;
}

</style>
