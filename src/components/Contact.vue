<script setup lang="ts"></script>
<template>
    <section class="contact">
        <h2>Contactez-moi !</h2>
        <form action="https://formspree.io/f/movkkynr" method="POST">
            <div class="form-group">
                <label for="name">Nom</label>
                <input id="name" name="name" type="text" placeholder="Votre nom..." />
            </div>

            <div class="form-group">
                <label for="email">Email</label>
                <input id="email" name="email" type="email" placeholder="Votre email..." />
            </div>

            <div class="form-group">
                <label for="message">Message</label>
                <textarea id="message" name="message" rows="5" placeholder="Votre message..."></textarea>
            </div>

            <button type="submit" class="btn-submit">Envoyer</button>
        </form>
    </section>
</template>
<style scoped>
/* =================================== */
/* Styles de base (Mobile First)       */
/* =================================== */

.contact-section {
  padding: 2rem 0;
  text-align: center;
}

.contact-section h2 {
  margin-bottom: 2rem;
}

/* Organisation du formulaire */
.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  max-width: 600px;
  margin: 0 auto;   /* Centrage du formulaire */
  text-align: left;
}

.form-group {
  display: flex;
  flex-direction: column;
}

/* Style des étiquettes (labels) */
.form-group label {
  margin-bottom: 0.5rem;
  font-weight: 500;
  color: var(--couleur-texte-secondaire);
}

/* Style des champs de saisie */
.form-group input,
.form-group textarea {
  background-color: rgba(39, 39, 42, 0.7);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 8px;
  padding: 0.8rem 1rem;
  color: var(--couleur-texte);
  font-size: 1rem;
  font-family: inherit;
  transition: border-color 0.3s ease;
}

/* Effet au focus pour les champs */
.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: var(--couleur-texte); /* La bordure devient blanche */
}
.btn-submit {
  /* Propriétés de base (.btn) */
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: .9rem 1.2rem;
  border-radius: 14px;
  font-weight: 600;
  text-decoration: none;
  transition: all .25s ease;
  border: 2px solid rgba(255, 255, 255, .25); /* Bordure neutre */
  backdrop-filter: saturate(140%) blur(2px);
  cursor: pointer;

  /* Propriétés de couleur (.btn-primary adapté) */
  color: #fff;
  background: rgba(255, 255, 255, .05); /* Fond neutre et subtil */
  box-shadow: 0 8px 24px rgba(0, 0, 0, .25); /* Ombre neutre */
}

.btn-submit:hover {
  transform: translateY(-2px);
  box-shadow: 0 14px 36px rgba(0, 0, 0, .35);
  border-color: #fff;
  background: rgba(255, 255, 255, .12);
}
</style>