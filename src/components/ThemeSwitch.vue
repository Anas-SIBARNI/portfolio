<script setup lang="ts">
import { ref, onMounted } from 'vue';

const theme = ref('light'); // Thème par défaut

const toggleTheme = () => {
  const newTheme = theme.value === 'light' ? 'dark' : 'light';
  theme.value = newTheme;
  document.body.classList.toggle('dark-theme', newTheme === 'dark');
  localStorage.setItem('theme', newTheme);
};

onMounted(() => {
  const savedTheme = localStorage.getItem('theme');
  if (savedTheme) {
    theme.value = savedTheme;
    document.body.classList.toggle('dark-theme', savedTheme === 'dark');
  }
});
</script>

<template>
  <label class="switch" for="theme-switch" aria-label="Changer de thème">
    <input type="checkbox" id="theme-switch" @change="toggleTheme" :checked="theme === 'dark'">
    <span class="slider">
      <svg class="icon lune" xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"></path></svg>
      <svg class="icon soleil" xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="5"></circle><line x1="12" y1="1" x2="12" y2="3"></line><line x1="12" y1="21" x2="12" y2="23"></line><line x1="4.22" y1="4.22" x2="5.64" y2="5.64"></line><line x1="18.36" y1="18.36" x2="19.78" y2="19.78"></line><line x1="1" y1="12" x2="3" y2="12"></line><line x1="21" y1="12" x2="23" y2="12"></line><line x1="4.22" y1="19.78" x2="5.64" y2="18.36"></line><line x1="18.36" y1="5.64" x2="19.78" y2="4.22"></line></svg>
    </span>
  </label>
</template>

<style scoped>
/* Le conteneur principal de l'interrupteur */
.switch {
  position: relative;
  display: inline-block;
  width: 60px;
  height: 34px;
  cursor: pointer;
}

/* On cache la case à cocher HTML par défaut */
.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

/* La "piste" de l'interrupteur */
.slider {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: var(--couleur-surface-fond);
  border: 1px solid var(--couleur-surface-bordure);
  border-radius: 34px;
  transition: background-color 0.4s;
}

/* Le "curseur" qui glisse */
.slider::before {
  content: "";
  position: absolute;
  height: 26px;
  width: 26px;
  left: 3px;
  bottom: 3px;
  background-color: #fff;
  border-radius: 50%;
  transition: transform 0.4s; /* C'est ça qui crée l'animation de glissement ! */
}

/* Quand la case est cochée, on déplace le curseur vers la droite */
input:checked + .slider::before {
  transform: translateX(26px);
}

/* Positionnement des icônes */
.icon {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  transition: opacity 0.4s;
}
.lune {
  left: 8px;
  opacity: 0; /* Cachée par défaut */
}
.soleil {
  right: 8px;
  opacity: 1; /* Visible par défaut */
}

/* On affiche la bonne icône selon l'état */
input:checked + .slider .lune {
  opacity: 1;
}
input:checked + .slider .soleil {
  opacity: 0;
}
</style>