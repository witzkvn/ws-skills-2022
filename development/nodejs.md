# Titre de la compétence

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- Comment développer en utilisant un système de _livereloading_ (`nodemon` par exemple) ✔️
  Ajout d'un script dans `package.json` de ce type :

```json
  "scripts": {
    "start": "nodemon server.js",
  },
```

- La connexion de mon application à une base de données avec et sans ORM/ODM (avec `mongodb` puis `mongoose` par exemple) ✔️
  On met les paramètres de connexion dans un fichier .env pour ne pas les exposer, puis on configure la connexion avec mongoose comme ceci (server.js) :

```javascript
// ...
dotenv.config({ path: "./config.env" });

const app = require("./app");

const DB = process.env.DATABASE.replace(
  "<password>",
  process.env.DATABASE_PASSWORD
);

mongoose
  .connect(DB)
  .then(() => console.log("Connexion with DB done. Listening to requests..."));

// app listen on port
```

- Le développement d'une API REST et GraphQL (avec les packages `express` et `graphql` par exemple) ❌ / ✔️
- _Bonus : la manipulation des fichiers système avec `fs` et l'utilisation des streams en NodeJS_ ❌ / ✔️

## 💻 J'utilise

### Un exemple personnel commenté ❌ / ✔️

```javascript
// this function takes a path to a .md file of the host system and write the HTML version of this file
// the .html file is given back
const convertMDFileToHTML = (pathToMDfile) => /* ... path to HTML file */
```

### Utilisation dans un projet ❌ / ✔️

[lien github](...)

Description :

### Utilisation en production si applicable❌ / ✔️

[lien du projet](...)

Description :

### Utilisation en environement professionnel ❌ / ✔️

Description :

## 🌐 J'utilise des ressources

### Titre

- lien
- description

## 🚧 Je franchis les obstacles

### Point de blocage ❌ / ✔️

Description:

Plan d'action : (à valider par le formateur)

- action 1 ❌ / ✔️
- action 2 ❌ / ✔️
- ...

Résolution :

## 📽️ J'en fais la démonstration

- J'ai ecrit un [tutoriel](...) ❌ / ✔️
- J'ai fait une [présentation](...) ❌ / ✔️
