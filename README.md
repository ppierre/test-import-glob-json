# Test import des JSON d'un dossier avec ViteJS

[`./src/App.vue :`](./src/App.vue#L2)
```js
//ViteJS peut importer tout les JS,JSON... d'un dossier :
const jsonsImport = import.meta.globEager("./assets/test-json/*.json");
```

Site visible à https://vite-import-json.netlify.app/

Si lancé avec le serveur de développement (Eg. `localhost:4000`) pour pouvoir utiliser la partie admin en local : lancer aussi `npm run netlify-proxy`