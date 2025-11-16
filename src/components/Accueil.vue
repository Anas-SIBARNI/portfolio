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
      <h1 class="nom">Anas Sibarni</h1>

      <h2 class="role-titre">Étudiant Développeur Full-Stack</h2>
      <p class="accroche">
        Actuellement en recherche active d'un stage (8-10 semaines, dès avril 2026) et d'une alternance pour ma 3ème année de BUT Informatique.
      </p>
      
      <a href="/cv_Anas_SIBARNI.pdf" download class="btn-cta">
        <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
          <polyline points="7 10 12 15 17 10"></polyline>
          <line x1="12" y1="15" x2="12" y2="3"></line>
        </svg>
        Télécharger mon CV
      </a>
      
      <div class="separateur">
      </div>

      <div class="liens-sociaux">
        
        <a href="https://github.com/Anas-SIBARNI" target="_blank" class="lien lien-logo-seul" aria-label="GitHub">
          <img src="/src/assets/competences/GitHub_Logo.png" alt="Logo GitHub" class="logo-social logo-light">
          <img src="/src/assets/competences/GitHub_Logo_White.png" alt="Logo GitHub" class="logo-social logo-dark">
        </a>
        
        <a href="https://www.linkedin.com/in/anas-sibarni/" target="_blank" class="lien lien-logo-seul" aria-label="LinkedIn">
          <img src="/src/assets/competences/LI-Logo.png" alt="Logo LinkedIn" class="logo-social">
        </a>

        <button @click="copierEmail" class="lien lien-email" aria-label="Copier l'email">
          <span class="icone-container">
            <svg :class="{ 'icone-active': !estCopie }" class="icone icone-mail" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
              <polyline points="22,6 12,13 2,6"></polyline>
            </svg>
            <svg :class="{ 'icone-active': estCopie }" class="icone icone-check" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <polyline points="20 6 9 17 4 12"></polyline>
            </svg>
          </span>
          <span class="texte-email">{{ estCopie ? 'Copié !' : 'Email' }}</span>
        </button>
      </div>
    </div>

    <div class="photo-container">
      <div class="photo-decoration"></div>
      <img src="/src/assets/photo-fond-transparent.png" alt="Photo de Anas Sibarni" />
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

.role-titre {
    font-size: 1.3rem;
    font-weight: 600;
    color: var(--couleur-texte);
    margin-top: 0;
    margin-bottom: 1.5rem;
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
    gap: 0.6rem; 
    /* MODIFIÉ : Padding vertical de 1.5rem (24px) pour tous les boutons */
    padding: 1.5rem 1.4rem;
    border-radius: 14px;
    font-weight: 600;
    text-decoration: none;
    transition: all 0.25s ease;
    border: 1px solid var(--couleur-surface-bordure);
    background: var(--couleur-surface-fond);
    color: var(--couleur-texte);
    font-family: inherit;
    font-size: 1rem;
    cursor: pointer;
    position: relative; 
    overflow: hidden; 
}

.lien:hover {
    border-color: var(--couleur-accent-action);
    transform: translateY(-3px); 
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1); 
}

.lien::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
    transition: all 0.6s ease;
    z-index: 0;
}

.lien:hover::before {
    left: 100%;
}

.lien > * { 
    position: relative;
    z-index: 1;
}

.lien-logo-seul {
    /* MODIFIÉ : Padding de 1.5rem partout pour respecter la guideline et être carré */
    padding: 1.5rem;
    gap: 0;
}

.logo-social {
    height: 24px; 
    width: auto;
    object-fit: contain;
    transition: filter 0.3s ease;
}

.lien span, .lien svg {
    color: var(--couleur-texte); 
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
    margin-bottom: 2.5rem;
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
        text-align: center;
        gap: 3rem;
        min-height: 90vh;
    }

    .contenu {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .accroche {
        margin: 0 0 2.5rem 0;
    }

    .nom {
        color: var(--couleur-accent);
        font-size: 4.5rem;
        margin-bottom: 1.5rem;
    }

    .role-titre {
        font-size: 1.5rem;
        margin-top: -1rem;
        margin-bottom: 2rem;
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
        width: 420px;
        height: 420px;
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

    .separateur {
        width: 100%;
        max-width: 500px;
        display: flex;
        align-items: center;
        justify-content: center;
        margin: 0rem 0 2.5rem 0;
        position: relative;
    }
    .separateur::before,
      .separateur::after {
        content: '';
        flex: 1;
        height: 1px;
        background: linear-gradient(90deg, transparent, var(--couleur-surface-bordure), transparent);
      }

    .liens-sociaux {
        justify-content: center;
        gap: 1.5rem;
    }
}

.logo-light {
  display: block;
}
.logo-dark {
  display: none;
}

:global(body.dark-theme) .logo-light {
  display: none;
}
:global(body.dark-theme) .logo-dark {
  display: block;
}
</style>