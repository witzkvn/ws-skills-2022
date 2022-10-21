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

- Le développement d'une API REST et GraphQL (avec les packages `express` et `graphql` par exemple) ✔️

  Exemple de projet REST : [Wilder Book REST](https://github.com/witzkvn/20220920_wilders_book_ts_backend)

  Exemple de projet GraphQL : [Wilder Book GraphQL](https://github.com/witzkvn/WCS_wilders_book_TS_GraphQL_BACK)

- _Bonus : la manipulation des fichiers système avec `fs` et l'utilisation des streams en NodeJS_ ❌ / ✔️

## 💻 J'utilise

### Un exemple personnel commenté ❌ / ✔️

```javascript

```

### Utilisation dans un projet ✔️

[Wilders Book en vanilla JS](https://github.com/witzkvn/20220912_nodejs_express_typeORM_sqlite_basics)

Description : Projet Backend en Vanilla JS Node avec typeORM, Express et SQLite

### Utilisation en production si applicable❌ / ✔️

[lien du projet](...)

Description :

### Utilisation en environement professionnel ❌ / ✔️

Description :

## 🌐 J'utilise des ressources

### Node JS doc

- https://nodejs.org/en/docs/
- Documentation de Node JS

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
