<script setup lang="ts">
import { ref } from 'vue';

const estCopie = ref(false);

async function copierEmail() {
  if (estCopie.value) return;
  try {
    await navigator.clipboard.writeText('anas.sibarni@gmail.com');
    estCopie.value = true;
    setTimeout(() => {
      estCopie.value = false;
    }, 2000);
  } catch (err) {
    console.error('Erreur lors de la copie du mail : ', err);
  }
}
</script>

<template>
  <section class="accueil-section">
    <div class="contenu">
      <p class="sous-titre">Étudiant en Informatique - Conception d'Application</p>
      <h1 class="nom">Anas Sibarni</h1>
      <p class="accroche">
        Actuellement en recherche active d'un stage (8-10 semaines, dès avril 2026) et d'une alternance pour ma 3ème année de BUT Informatique.
      </p>
      <a href="/cv_Anas_SIBARNI.pdf" download class="btn-cta">Téléchargez mon CV !</a>
    </div>

    <div class="photo-container">
      <img src="/src/assets/photo-fond-transparent.png" alt="Photo de Anas Sibarni" />
      <div class="liens-sociaux">
        <a href="https://github.com/Anas-SIBARNI" target="_blank" class="lien" aria-label="GitHub">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path></svg>
        </a>
        <a href="https://www.linkedin.com/in/anas-sibarni/" target="_blank" class="lien" aria-label="LinkedIn">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect x="2" y="9" width="4" height="12"></rect><circle cx="4" cy="4" r="2"></circle></svg>
        </a>
        <button @click="copierEmail" class="lien" aria-label="Copier l'email">
          <div class="icone-container">
            <svg :class="{ 'icone-active': !estCopie }" class="icone" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline></svg>
            <svg :class="{ 'icone-active': estCopie }" class="icone" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>
          </div>
        </button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.accueil-section {
  min-height: 90vh; 
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 1rem;
}
.photo-container img {
  display: none;
}
.nom {
  font-size: 2.8rem;
  font-weight: 700;
  margin: 0 0 0.5rem 0;
}
.sous-titre {
  font-size: 1.1rem;
  color: var(--couleur-texte-secondaire);
  margin-bottom: 0.5rem;
  font-weight: 600;
}
.accroche {
  max-width: 500px;
  margin: 0 auto 2rem auto;
  color: var(--couleur-texte-secondaire);
}
.liens-sociaux {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
}
.lien {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 0.8rem;
  padding: 0.9rem 1.4rem;
  border-radius: 14px;
  font-weight: 600;
  text-decoration: none;
  transition: .25s ease;
  border: 1px solid var(--couleur-surface-bordure);
  background: var(--couleur-surface-fond);
  color: var(--couleur-texte);
  font-family: inherit;
  font-size: 1rem;
  cursor: pointer;
}
.lien:hover {
  border-color: var(--couleur-accent-action);
  transform: scale(1.1);
}
.lien svg {
  width: 20px;
  height: 20px;
  stroke: var(--couleur-texte);
}
.icone-container {
  position: relative;
  width: 20px;
  height: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.icone {
  position: absolute;
  transition: transform 0.3s ease-out, opacity 0.3s ease-out;
}
.icone.icone-active {
  transform: scale(1);
  opacity: 1;
}
.icone:not(.icone-active) {
  transform: scale(0);
  opacity: 0;
}
.btn-cta {
  display: inline-block;
  background-color: var(--couleur-accent);
  color: var(--couleur-fond);
  padding: 1rem 2.5rem;
  border-radius: 999px;
  text-decoration: none;
  font-weight: 700;
  font-size: 1.1rem;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  box-shadow: 0 10px 30px -10px var(--couleur-accent);
  margin-bottom: 2.5rem; /* Espace avant les liens sociaux sur mobile */
}
.btn-cta:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 40px -8px var(--couleur-accent);
}

@media (min-width: 992px) {
  .accueil-section {
    display: grid;
    grid-template-columns: 1.5fr 1fr;
    align-items: center;
    text-align: left;
    gap: 3rem;
    min-height: 90vh;
  }
  .contenu {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }
  .accroche {
    margin: 0 0 2.5rem 0; /* Espace pour le bouton CTA */
  }
  .nom {
    color: var(--couleur-accent);
    font-size: 4.5rem;
    margin-bottom: 1.5rem;
  }
  .sous-titre {
    margin-bottom: 1rem;
  }
  .photo-container {
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    min-height: auto;
    width: 100%;
    height: 100%;
  }
  .photo-container img {
    display: block;
    width: 380px;
    height: 380px;
    object-fit: cover;
    border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%;
    box-shadow: 0 15px 50px rgba(0, 0, 0, 0.2);
    animation: blob-morph 15s ease-in-out infinite;
    transition: all 0.5s ease-in-out;
  }
  .photo-container:hover img {
    border-radius: 50%;
  }
  
@keyframes blob-morph {

0% {

border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%;

}

50% {

border-radius: 30% 60% 70% 40% / 50% 60% 30% 60%;

}

100% {

border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%;

}

}


.liens-sociaux {

position: absolute;

bottom: 100px;

left: 10px;

width: 320px;

height: 200px;

display: block;

}



.lien {

position: absolute;

width: 90px;

height: 90px;

padding: 0;

border-radius: 50%;

border-width: 2px;

box-shadow: 0 5px 15px rgba(0,0,0,0.15);

transition: transform 0.3s ease-out;

}



.lien:hover {

transform: scale(1.15) !important;

z-index: 10;

}



.lien svg {

width: 50px;

height: 50px;

}

.icone-container {

width: 50px;

height: 50px;

}

.icone {

top: 0;

left: 0;

}.lien:nth-child(1) { /* GitHub */

bottom: 20%;

left: -11%; /* On le décale plus à gauche */

transform: rotate(-15deg);

}

.lien:nth-child(2) { /* LinkedIn */

bottom: -5%; /* On le décale vers le bas */

left: 10%;

transform: rotate(5deg);

}

.lien:nth-child(3) { /* Email */

bottom: -15%; /* On le décale encore plus bas */

left: 35%;

transform: rotate(15deg);

}

}
</style>