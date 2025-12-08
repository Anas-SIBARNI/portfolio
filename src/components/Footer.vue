<script setup lang="ts">
</script>

<template>
  <footer class="site-footer">
    <div class="footer-content">
      <p class="availability">
        En echerche active d'un stage et d'une alternance en développement d'applications.
      </p>

      <p class="contact-info">
        Contactez-moi : 
        <a href="mailto:anas.sibarni@gmail.com">anas.sibarni@gmail.com</a>
      </p>

      <p class="tech-mention">
        Site développé en Vue.js.
      </p>
    </div>
  </footer>
</template>

<style scoped>
.site-footer {
  background-color: var(--couleur-surface-fond);
  border-top: 1px solid var(--couleur-surface-bordure);
  padding: 2rem; /* Plus d'espace vertical */
  margin-top: 4rem;
  text-align: center; /* Tout est centré */
}

.footer-content {
  max-width: 800px; /* Limite la largeur du contenu */
  margin: 0 auto;
}

.availability {
  font-weight: 600; /* Met en avant la recherche */
  color: var(--couleur-accent); /* Utilise la couleur d'accent */
  margin: 0 0 1rem 0;
}

.contact-info {
  margin: 0 0 1rem 0;
}

.contact-info a {
  color: var(--couleur-accent-action);
  text-decoration: underline; 
}

.tech-mention {
  font-size: 0.85rem;
  color: var(--couleur-texte-secondaire);
  margin: 0;
}
</style>