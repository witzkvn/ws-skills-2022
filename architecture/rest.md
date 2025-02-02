# REST API

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les verbes ✔️

Il s'agit de verbes qui indiquent l'action à réaliser via la requêtes. Voici les principaux :

- GET : recevoir des données
- POST : envoyer des données
- PATCH : mettre à jour une donnée existante
- PUT : mettre à jour une donnée en la remplaçant totalement
- DELETE : supprimer des données
  <br/><br/>
- les statuts HTTP ✔️

Il s'agit d'un numéro qui permet d'indiquer le statut de la réponse à une requête. En particulier :

- 200 à 299 : succès
- 300 à 399 : redirection
- 400 à 499 : erreur client (par ex 404 Not Found)
- 500 à 599 : erreur serveur
  <br/><br/>
- les endpoints ✔️

Il s'agit des routes d'une API accessibles. Par exemple :
/api/v1/users : endpoint qui va renvoyer vers un userController chargé de gérer toute la logique, en fonction du type de requête (POST, GET...) mais aussi des paramètres et du body de la requête.
<br/><br/>

- CORS ✔️

  Acronyme de Cross-Origin Resource Sharing
  C'est un mécanisme qui permet d'échanger des fichiers entre domaines différents. Par défaut, un front et un back tournant sur des domaines différents ne pourront pas communiquer à cause de ce mécanisme qui bloque ces échanges (sécurité). Il faudra explicitement autoriser, en back, les requêtes venant d'un autre domaine

```javascript
app.use(cors()))
```

- la nomenclature recommandée pour les routes ✔️

  Utiliser des noms, qui sont clairs et indiquent de façon évidente la cible de la route. Par exemple `/api/v1/users` va référer aux actions sur les objets users en back.
  On écrit tout en minuscule en évitant les caractères spéciaux. Les verbes d'actions servent aussi à comprendre le but de la route. On utilise des slash "/" pour montrer la hiérarchie. Exemple complet : `GET /api/v1/users/:userid/firstname` est une route qui va renvoyer le prénom d'un user en fonction de son id.

## 💻 J'utilise

### Un exemple personnel commenté ✔️

Example d'un controller qui définit la méthode create d'un Skill

```typescript
// définition du endpoint
app.get("/api/skills", skillController.getAll);
```

```typescript
const skillController: IController = {
  // méthode getAll qui est en charge de renvoyer toutes les entités Skills de la BDD
  getAll: async (req, res) => {
    // trycatch pour gérer les erreurs
    try {
      // appel asynchrone qui requête notre BDD pour récupérer toutes les entités Skill
      const allSkills = await dataSource.getRepository(Skill).find();
      // si aucune erreur, renvoi de la réponse avec un status code de 200 (succès) et un body JSON avec les skills
      res.status(200).send({ message: "Success", skills: allSkills });
    } catch (error) {
      // en cas d'erreur, envoi de la réponse avec un status code 500 (internal server error) et un body JSON avec un message d'erreur
      res.status(500).send({ message: "Error while creating skill" });
    }
  },
  // ...
};
```

### Utilisation dans un projet ✔️

[Wilders Book REST](https://github.com/witzkvn/20220920_wilders_book_ts_backend)

Description : Création d'une application Backend permettant un CRUD sur les entités Wilders, de type API REST.

### Utilisation en production si applicable❌ / ✔️

[lien du projet](...)

Description :

### Utilisation en environement professionnel ❌ / ✔️

Description :

## 🌐 J'utilise des ressources

### Express JS

- https://expressjs.com/fr/starter/installing.html
- Documentation d'Express JS

### Postman

- https://www.postman.com/
- Postman pour tester les requêtes au serveur

### Mongoose

- https://mongoosejs.com/docs/guide.html
- Mongoose simplifie grandement l'interaction avec une BDD mongoDB

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
