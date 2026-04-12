<script setup lang="ts">
// components
import ThemeSwitch from './components/ThemeSwitch.vue';
import Navbar from './components/Navbar.vue';
import Accueil from './components/Accueil.vue';
import Competences from './components/Competences.vue';
import Formation from './components/Formation.vue';
import Realisations from './components/Realisations.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';

// logos
import python from './assets/competences/py.png';
import psql from './assets/competences/psql.png';
import jdbc from './assets/competences/jdbc.png';
import git from './assets/competences/git.png';
import docker from './assets/competences/docker.svg';
import tomcat from './assets/competences/tomcat.jpg';
import n8n from './assets/competences/n8n-white.png';


// aperçus projets
import bumplessImg from './assets/screens-projects/bumpless.png';
import flexipassImg from './assets/screens-projects/flexipass.png';
import sirtetImg from './assets/screens-projects/sirtet.png';
import mazyImg from './assets/screens-projects/mazy.png';
import portfolioImg from './assets/screens-projects/portfolio.png';
import stockPro from './assets/screens-projects/stockpro.png';
import clickme from './assets/screens-projects/clickme.png';
import bumpless2 from './assets/screens-projects/bumpless2.png';



const projets = [
  {
    id: 0,
    titre: 'Bumpless 2 - Jeu de tir multi-joueur',
    description: 'Jeu de combat avec tanks, 2 modes solo et multi-joueur. Équipe de 3, git partagé multi-branch. Architecture Client/Serveur.',
    outils: ['TypeScript', 'Node.js', 'HTML', 'CSS', 'Tailwind'],
    image: bumpless2, 
    githubUrl: 'https://github.com/Anas-SIBARNI/Bumpless-2'
  },
  {
    id: 1,
    titre: 'Mazy - Jeu de labyrinthes procéduraux',
    description: 'Jeu de labyrinthes 2D développé en équipe. Architecture MVC, principes SOLID (Clean Code) et campagne de tests unitaires.',
    outils: ['Java', 'JavaFX', 'JUnit', 'Maven', 'Git'],
    image: mazyImg, 
    githubUrl: 'https://github.com/Anas-SIBARNI/mazy'
  },
  {
    id: 2,
    titre: 'StockPro - Landing page',
    description: 'Développent d’une landing page statique pour un SaaS de gestion de stock qui n’existe pas encore',
    outils: ['React', 'HTML', 'TypeScript', 'Tailwind CSS'],
    image: stockPro,
    galerie: [stockPro],
    githubUrl: 'https://github.com/Anas-SIBARNI' 
  },
  {
    id: 3,
    titre: 'ClickMe - Jeu de clique',
    description: 'Jeu consistant à cliquer sur un bouton. Authentification, sauvegarde des scores, scoreboard via Supabase.',
    outils: ['Angular','Supabase', 'TypeScript', 'Tailwind CSS', 'HTML'],
    image: clickme,
    galerie: [clickme],
    githubUrl: 'https://github.com/Anas-SIBARNI' 
  },
  {
    id: 4,
    titre: 'Bumpless - Jeu de combat de chars',
    description: 'Jeu en 1v1 en temps réel avec système de bonus/malus, collisions, classement des scores et persistance simple en CSV. Avec interface graphique !',
    outils: ['Python', 'Pygame', 'CSV', 'Pandas'],
    image: bumplessImg,
    githubUrl: 'https://github.com/Anas-SIBARNI/Bumpless' 
  },
  {
    id: 5,
    titre: 'Sirtet - Jeu de briques dans un terminal',
    description: 'Jeu de briques en temps réel développé en équipe selon la méthode agile, avec sauvegarde des scores.',
    outils: ['Java', 'Lanterna'],
    image: sirtetImg,
    githubUrl: 'https://github.com/Anas-SIBARNI/Sirtet' 
  },
  {
    id: 6,
    titre: 'FlexiPass - Gestionnaire de mot de passe',
    description: 'Logiciel d\'un générateur de mots de passe personnalisable, avec copie dans le presse-papiers et enregistrement.',
    outils: ['Python', 'CustomTkinter', 'Pyperclip'],
    image: flexipassImg,
    githubUrl: 'https://github.com/Anas-SIBARNI/FlexiPass'
  },
  {
    id: 7,
    titre: 'Portfolio - (ce site)',
    description: 'Plateforme web pour présenter mon profil et mes projets. Ce portfolio a été développé avec Vue.js, un framework appris en dehors de mon cursus universitaire...',
    outils: ['Vue.js', 'Vite', 'Typescript', 'HTML5', 'CSS3', 'Vibe Coding'],
    image: portfolioImg,
    githubUrl: 'https://github.com/Anas-SIBARNI/portfolio'
  },

  
  
];
const competences = {
  programmation: [
    { nom: 'Java', logo: 'https://dev.java/assets/images/java-affinity-logo-icode-lg.png' },
    { nom: 'Python', logo: python },
    { nom: 'C', logo: 'https://icongr.am/devicon/c-original.svg?size=128&color=currentColor'}
  ],
  web: [
    { nom: 'HTML5', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original.svg' },
    { nom: 'CSS3', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original.svg' },
    { nom: 'JavaScript', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-plain.svg' },
    { nom: 'TypeScript', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/typescript/typescript-plain.svg' },
    { nom: 'Node.js', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nodejs/nodejs-plain-wordmark.svg' },
    { nom: 'Vue.js', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original.svg' },
    { nom: 'React', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/react/react-original.svg' },
    { nom: 'Angular', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/angular/angular-original.svg' },
    { nom: 'Tailwind CSS', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/tailwindcss/tailwindcss-original.svg' },
    { nom: 'BootStrap', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/bootstrap/bootstrap-original.svg' },
    { nom: 'Vite', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vitejs/vitejs-original.svg' }
  ],
  baseDeDonnees: [
    { nom: 'SQL', logo: 'https://www.svgrepo.com/show/331760/sql-database-generic.svg' },
    { nom: 'PostgreSQL', logo: psql },
    { nom: 'JDBC', logo: jdbc },
    { nom: 'Supabase', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/supabase/supabase-original.svg' }
  ],
  divers: [
    { nom: 'Nginx', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nginx/nginx-original.svg' },
    { nom: 'Tomcat', logo: tomcat },
    { nom: 'Docker', logo: docker },
    { nom:'Git', logo: git },
    { nom: 'n8n', logo: n8n},
    { nom: 'IntelliJ', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/intellij/intellij-original.svg' },
    { nom: 'VS Code', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vscode/vscode-original.svg' }

  ]
};

const formations = [
  { 
    id: 1,
    annee: "2024 - Aujourd'hui",
    titre: "Bachelor Universitaire de Technologie - Informatique - Parcours réalisation d'applications",
    etablissement: "Université de Lille - Villeneuve d'Ascq"
  },
  { 
    id: 2,
    annee: "Juillet 2024",
    titre: "Baccalauréat Général - Section européenne (Anglais) - Mention Bien",
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
    <Footer />
  </main>
</template>
<style>

</style>
