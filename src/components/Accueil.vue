<script setup lang="ts">
// Pour l'instant, nous n'avons pas besoin de code TypeScript ici.
// Ce composant est purement visuel.
</script>

<template>
  <section class="accueil-section">
    <div class="contenu">
      <h1 class="nom">Anas Sibarni</h1>
      <p class="sous-titre">Étudiant en Informatique - Conception d'Application</p>
      <p class="accroche">
        En 2ème année de BUT Informatique, je suis à la recherche d'un stage de 8 à 10 semaines à partir d'avril 2026 et d'une alternance pour ma 3ème année.
      </p>
      <div class="liens-sociaux">
        <a href="https://github.com/Anas-SIBARNI" target="_blank">GitHub</a>
        <a href="https://www.linkedin.com/in/anas-sibarni/" target="_blank">LinkedIn</a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.accueil-section {
  position: relative; /* Nécessaire pour le positionnement du contenu */
  min-height: 90vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.contenu {
  text-align: center;
}

.sous-titre {
  margin-bottom: 1rem;
  color: #ccc;
  font-size: 1rem;
  font-weight: 600;
}

.nom {
  color: #fff;
  margin-bottom: 1rem;
  font-size: 3.5rem;
  font-weight: 700;
  line-height: 4.5rem;
  letter-spacing: .5px;
}


.accroche {
  max-width: 600px;
  margin: 0 auto 2rem auto;
  color: rgba(220,220,235,.85);
}

.liens-sociaux a {
  margin: 0 0.5rem;
  padding: .9rem 1.2rem;
  border-radius: 14px;
  font-weight: 600;
  text-decoration: none;
  transition: .25s ease;
  border: 1px solid rgba(255,255,255,.25);
  background: rgba(255,255,255,.05);
  color: #fff;
}

.liens-sociaux a:hover {
  border-color: #fff;
  background: rgba(255,255,255,.12);
}
</style>