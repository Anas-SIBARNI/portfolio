<script setup lang="ts">
defineProps(['projets'])
</script>

<template>
  <section>
    <h2>Mes Projets</h2>
    <ul>
      <li v-for="projet in projets" :key="projet.id">
        {{ projet.titre }}
      </li>
    </ul>
  </section>
</template>

<style scoped>

</style>