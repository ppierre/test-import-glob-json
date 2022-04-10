<script setup>
//ViteJS peut importer tout les JS,JSON... d'un dossier :
const jsonsImport = import.meta.globEager("./assets/test-json/*.json");
// Il est mieux d'importer les données dans un fichier dédié, puis d'importer l'export de ce fichier :
// import { jsonsImport } from "./test-json-import.js";
import { useRoute } from "vue-router";
const route = useRoute();
</script>

<template>
  <div v-if="route.name === 'index'">
    <h1>Test import des JSON d'un dossier</h1>
    <h3>Contenu "brut" de la variable :</h3>
    <code>
      <pre>
    const jsonsImport = import.meta.globEager("./assets/test-json/*.json");</pre
      >
    </code>
    <code>
      <pre>
        {{ JSON.stringify(jsonsImport, null, 4) }}
      </pre>
    </code>
    <h3>Donc facile de faire une boucle... :</h3>
    <ul>
      <li v-for="(jsonContent, fileName) in jsonsImport" :key="fileName">
        <p>
          Nom de fichier <code>{{ fileName }}</code>
        </p>
        <ul>
          <li>id: {{ jsonContent.id }}</li>
          <li>title: {{ jsonContent.title }}</li>
        </ul>
      </li>
    </ul>
  </div>
  <h3>Si l'on ajoute "file based router" :</h3>
  <router-view />
  <hr />
  <a href="/admin/index.html"
    >Lien vers le "back office" fait par Netlify CMS
  </a>
</template>
