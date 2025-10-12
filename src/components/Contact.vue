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
</template><style scoped>
.contact-section {
  padding: 2rem 0;
  text-align: center;
}

.contact-section h2 {
  margin-bottom: 2rem;
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  max-width: 600px;
  margin: 0 auto;
  text-align: left;
}

.form-group {
  display: flex;
  flex-direction: column;
}

.form-group label {
  margin-bottom: 0.5rem;
  font-weight: 500;
  color: var(--couleur-texte-secondaire);
}

.form-group input,
.form-group textarea {
  background-color: var(--couleur-surface-fond);
  border: 1px solid var(--couleur-surface-bordure);
  border-radius: 8px;
  padding: 0.8rem 1rem;
  color: var(--couleur-texte);
  font-size: 1rem;
  font-family: inherit;
  transition: border-color 0.3s ease;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: var(--couleur-accent-action);
}

.btn-submit {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: .9rem 1.2rem;
  border-radius: 14px;
  font-weight: 600;
  text-decoration: none;
  transition: all .25s ease;
  cursor: pointer;
  
  border: 2px solid var(--couleur-surface-bordure);
  background: var(--couleur-surface-fond);
  color: var(--couleur-texte);
}

.btn-submit:hover {
  transform: translateY(-2px);
  border-color: var(--couleur-accent-action);
  background: var(--couleur-surface-survol-fond);
}
</style>