<script setup>
import { jsonsImport } from "../test-json-import.js";
</script>
<template>
  <h4>fichier src\pages\test-json.vue</h4>
  <p><router-link to="/">Retour à "index"</router-link></p>
  <p>affiche la collection du dossier <code>src/assets/test-json</code></p>
  <ul>
    <!-- En faite, en vuejs c'est plus simple si l'on boucle seulement sur les valeurs de l'objet -->
    <li v-for="jsonContent of jsonsImport" :key="jsonContent.id">
      <router-link :to="`/test-json/${jsonContent.id}`">{{
        jsonContent.title
      }}</router-link>
    </li>
  </ul>
</template>