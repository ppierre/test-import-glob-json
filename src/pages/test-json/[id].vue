<script setup>
import { jsonsImport } from "../../test-json-import.js";
const props = defineProps({
  id: { type: String },
});
const currentJson = Object.values(jsonsImport).find(
  ({ id: aId }) => aId == props.id // conversion implicite de nombre en chaine, mais fct avec uuid
);
import { Remarkable } from "remarkable";
const md = new Remarkable();
const bodyHTML = md.render(currentJson.body);
</script>

<template>
  <div>
    <h1>Le titre : {{ currentJson.title }}</h1>
    <h4>fichier <code>src\pages\test-json/[id].vue</code></h4>
    <p>L'on a <code>id</code> qui vaut : {{ id }}</p>
    <h4>Markdown brut</h4>
    <pre>
      {{ currentJson.body }}
    </pre>
    <h4>Code convrti en HTML</h4>
    <pre>{{ bodyHTML }}</pre>
    <h4>Rendu</h4>
    <div style="border: solid black" v-html="bodyHTML"></div>
    <p><router-link to="/test-json">Retour à la liste</router-link></p>
  </div>
</template>