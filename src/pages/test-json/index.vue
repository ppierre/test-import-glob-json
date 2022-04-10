<script setup>
// fichier changé de test-json.vue à test-json/index.vue pour ne pas masquer test-json/[id].vue
import { jsonsImport } from "../../test-json-import.js";
</script>
<template>
  <h4>fichier src\pages\test-json/index.vue</h4>
  <p><router-link to="/">Retour à "index"</router-link></p>
  <p>affiche la collection du dossier <code>src/assets/test-json</code></p>
  <ul>
    <!-- En faite, en vuejs c'est plus simple si l'on boucle seulement sur les valeurs de l'objet -->
    <li v-for="jsonContent of jsonsImport" :key="jsonContent.id">
      <!-- <router-link :to="`/test-json/${jsonContent.id}`">{{ -->
      <router-link
        :to="{ name: 'test-json-id', params: { id: jsonContent.id } }"
        >{{ jsonContent.title }}</router-link
      >
    </li>
  </ul>
</template>