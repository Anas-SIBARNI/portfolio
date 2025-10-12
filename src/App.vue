<script setup lang="ts">
import Navbar from './components/Navbar.vue';
import Accueil from './components/Accueil.vue';
import Competences from './components/Competences.vue';
import Formation from './components/Formation.vue';
import Realisations from './components/Realisations.vue';
import Contact from './components/Contact.vue';


const projets = [
  {
    id: 1,
    titre: 'si-chat.app - Messagerie web en temps réel',
    description: "Application de messagerie avec authentification, discussions privées/groupes, profils avec photo, et persistance des messages.",
    technologies: ['HTML5', 'CSS3', 'JavaScript', 'Node.js', 'Express', 'Socket.IO', 'PostgreSQL', 'Nginx']
  },
  {
    id: 2,
    titre: 'Bumpless - Jeu de combat de chars',
    description: 'Jeu en 1v1 en temps réel avec système de bonus/malus, collisions, classement des scores et persistance simple en CSV.',
    technologies: ['Python', 'Pygame', 'CSV', 'Pandas']
  },
  {
    id: 3,
    titre: 'FlexiPass - Gestionnaire de mot de passe',
    description: 'Générateur de mots de passe personnalisables avec copie dans le presse-papiers et enregistrement sécurisé.',
    technologies: ['Python', 'CustomTkinter', 'Pyperclip']
  },
  {
    id: 4,
    titre: 'Sirtet - Jeu de briques dans un terminal',
    description: 'Jeu de briques en temps réel développé en équipe de 5 jours selon la méthode agile, avec sauvegarde des scores.',
    technologies: ['Java', 'Lanterna']
  }
];
const competences = {
  langages: [
    { nom: 'Java', logo: null },
    { nom: 'Python', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original.svg' },
    { nom: 'C', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/c/c-original.svg' },
    { nom: 'SQL', logo: null },
    { nom: 'HTML5', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original.svg' },
    { nom: 'CSS3', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original.svg' },
  ],
  baseDeDonnees: [
    { nom: 'PostgreSQL', logo: null },
    { nom: 'Microsoft Access', logo: null }
  ],
  deploiement: [
    { nom: 'Nginx', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nginx/nginx-original.svg' },
    { nom: 'PM2', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/pm2/pm2-original.svg' }
  ]
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
