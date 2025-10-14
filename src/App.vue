<script setup lang="ts">
import ThemeSwitch from './components/ThemeSwitch.vue';
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
    description: 'Générateur de mots de passe personnalisables avec copie dans le presse-papiers et enregistrement.',
    technologies: ['Python', 'CustomTkinter', 'Pyperclip']
  },
  {
    id: 4,
    titre: 'Sirtet - Jeu de briques dans un terminal',
    description: 'Jeu de briques en temps réel développé en équipe selon la méthode agile, avec sauvegarde des scores.',
    technologies: ['Java', 'Lanterna']
  },
  {
    id: 5,
    titre: 'Portfolio - Mon portfolio que vous voyez actuellement',
    description: 'Présentation de qui je suis, qu\'est-ce que j\'ai fait, qu\'est-ce que je sais faire, formulaire de contact. Utilisation d\'une technologie (Vue.js) qu\'on ne nouos enseigne pas en cours !',
    technologies: ['Vue.js', 'Typescript', 'HTML5', 'CSS3']
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
  ],
  depots: [
    { nom:'Gitlab', logo: null},
    { nom:'Github', logo: null},
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
  <Navbar />
  <main>
    <ThemeSwitch />
    <Accueil id="accueil" />
    <Competences id="competences" :competences="competences" />
    <Formation id="formation" :formations="formations" />
    <Realisations id="realisations" :projets="projets" />
    <Contact id="contact" />
  </main>
</template>
<style>

</style>
