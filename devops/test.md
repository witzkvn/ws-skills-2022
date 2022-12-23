# Tester son application

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les tests unitaires ✔️

  Ce sont des tests simples comme les test d'une fonction, en fournissant X params on reçoit Y réponse de la fonction.

- les mocks ✔️

  Ce sont des fausses data qui servent à remplacer des données, des fonctions, que l'on obtiendrait normalement autrement. Par exemple, si une fonction nécessite de fetch un objet user en DB, on va créer un mock object d'un user que l'on va passer à la fonction dans les tests pour vérifier que tout fonctionne comme attendu.

- les tests d'integration ✔️

  Il s'agit de tests qui vérifient l'imbrication de plusieurs bouts de code ensemble. Par exemple en back, telle requête entrante va appeler tel controller, telle méthode, qui va renvoyer telle réponse. On test un cheminement plutôt que les fonctions individuellement comme les tests unitaires.

- les tests de bout en bout (end to end) ✔️

  Ici on test un parcours complet du front-back-front : telle action en front doit entrainer tel appel au back, qui est géré de telle ou telle façon, puis renvoie telle réponse, qui est reçue et traitée de telle façon visuellement. On simule un cas réel d'utilisation de l'application et on test que l'ensemble fonctionne comme attendu.

- le TDD ✔️

  Il s'agit d'une méthode de travail qui consiste à d'abord écrire les tests d'une nouvelle fonctionnalité, puis d'écrire le code pour cette fonctionnalité et de s'assurer que tous les tests écrits passent.

- les tests par snapshot ✔️
  On peut prendre des captures à un instant T de l'état de l'application durant le test, et vérifier que cet état répond aux attentes dans des tests.

## 💻 J'utilise

### Un exemple personnel commenté ✔️

```javascript
import { ITestUser } from "src/interfaces/entitites/testUserInterface";
import clearDB from "./helpers/clearDB";
import { generateTestAdmin } from "./helpers/generate/user/generateTestAdmin";
import { getTokenForUser } from "./helpers/generate/user/getTokenForUser";
import client from "./helpers/getClient";
import { CREATE_ACTIVITY_TYPE } from "./helpers/graphql/mutations/activityType/createActivityType";
import { GET_ALL_ACTIVITY_TYPES } from "./helpers/graphql/queries/actitityType/getAllActivityType";

describe("ActivityType resolver", () => {
  // global entities that can be reused accross tests
  let testAdmin: ITestUser;
  let testAdminToken: string;

  // executed before all tests : instantiation of global entities
  beforeAll(async () => {
    testAdmin = await generateTestAdmin();
    testAdminToken = await getTokenForUser("test", testAdmin.email);
  });

  // clear all entities in database after all tests to start the next ones fresh
  afterAll(async () => {
    await clearDB();
  });

  // basic test with a query
  it("get all activityTypes", async () => {
    const res = await client.query({
      query: GET_ALL_ACTIVITY_TYPES,
      fetchPolicy: "no-cache",
    });
    expect(res.data?.getAllActivityTypes).toEqual([]);
  });

  // basic test with a mutation, and we pass a token for authorization
  it("create activityType", async () => {
    const res = await client.mutate({
      mutation: CREATE_ACTIVITY_TYPE,
      variables: {
        name: "transport",
      },
      fetchPolicy: "no-cache",
      context: {
        headers: {
          authorization: testAdminToken,
        },
      },
    });
    expect(res.data.createActivityType.name).toEqual("transport");
  });
});
```

### Utilisation dans un projet ✔️

[Projet de groupe Wildcarbon](https://github.com/WildCodeSchool/2209-wns-rivest-groupe5-root)

Description :

### Utilisation en production si applicable❌ / ✔️

[lien du projet](...)

Description :

### Utilisation en environement professionnel ✔️

Description : Si le projet Job Success, mise en place de tests d'intégration et de tests unitaires côté backend.
Exemple d'un test unitaire d'une fonction chargée de vérifier le format d'un mot de passe

```javascript
import passwordIsValid from "../../../src/utils/passwordValidation";

describe("Test password validity", () => {
  it("return false if empty", () => {
    expect(passwordIsValid("")).toBe(false);
  });
  it("return false if less than 8 caracters", () => {
    expect(passwordIsValid("abcdefg")).toBe(false);
  });
  it("return false if no capital letter", () => {
    expect(passwordIsValid("abcdefgh")).toBe(false);
  });
  it("return false if no minus letter", () => {
    expect(passwordIsValid("ABCDEFGH")).toBe(false);
  });
  it("return false if no letter", () => {
    expect(passwordIsValid("1234*/@$")).toBe(false);
  });
  it("return false if no number", () => {
    expect(passwordIsValid("Abcdefgh")).toBe(false);
  });
  it("return false if no special caracters", () => {
    expect(passwordIsValid("Abcdefg3")).toBe(false);
  });
  it("return true if at least 8 caracters, one maj, one min, one special caracter", () => {
    expect(passwordIsValid("ABcd1234*")).toBe(true);
  });
});
```

Et exemple d'un test d'intégration sur la route update password

```javascript
describe("PATCH update password for User", () => {
  describe("given a wrong passwordCurrent for the requesting user", () => {
    it("should return an UNAUTHORIZED 401 error", async () => {
      const reqBody = {
        passwordCurrent: "wrongPass12*",
        password: "UpdatedPass123*",
        passwordConfirm: "UpdatedPass123*",
      };

      const res = await request(app)
        .patch(`/api/v1/users/update-password`)
        .set("Authorization", `Bearer ${userJWT}`)
        .send(reqBody);

      testResponseBody(
        res,
        "error",
        401,
        `/api/v1/users/update-password`,
        true,
        "PATCH"
      );
    });
  });
  // ...
});
```

## 🌐 J'utilise des ressources

### JEST

- https://jestjs.io/fr/docs/getting-started
- Jest documentation

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
