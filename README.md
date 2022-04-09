# Test import des JSON d'un dossier avec ViteJS

[`./src/App.vue :`](./src/App.vue#L2)
```js
//ViteJS peut importer tout les JS,JSON... d'un dossier :
const jsonsImport = import.meta.globEager("./assets/test-json/*.json");
```