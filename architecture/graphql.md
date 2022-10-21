# GraphQL

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- la différence entre REST et GraphQL ✔️

  REST est basé sur des endpoints avec des verbes (GET, POST, PATCH, DELETE...), tandis que GraphQL offre un seul endpoint avec des requêtes de type POST, et c'est du côté client qu'on défini un schéma décrivant la requête (une query pour recevoir des données, et pour tout le reste des mutations)

- les besoins auxquels répond GraphQL ✔️

  GraphQL permet de définir exactement ce dont on a besoin de récupérer dans la requête : pas d'overfetching (requête qui renverrait plus de données que nécessaire) et pas d'underfetching (pas assez de données dans la requête, ce qui implique d'en faire plusieurs pour atteindre le but)

- la définition d'un schéma ✔️

  C'est la description des data auxquelles le client peut accéder via l'API GraphQL. Par exemple le schema d'une entité Book :

```typescript
type Book {
  title: String
  author: Author
}
```

- Query ✔️

  C'est une requête qui permet de récupérer des données sans les modifier (équivalent GET en API REST)

- Mutation ✔️

  C'est une requête qui permet de modifier des données (équivalent à du PUT, PATCH, DELETE, POST d'une API REST)

- Subscription ❌ / ✔️

## 💻 J'utilise

### Un exemple personnel commenté ✔️

Exemple frontend

```typescript
import { gql } from "@apollo/client";

// define the frontend schema to query all skills
export const GET_ALL_SKILLS = gql`
  query GetAllSkills {
    # for each skill, retrieve id and name
    getAllSkills {
      id
      name
    }
  }
`;
```

Le resolver backend qui gère cette query

```typescript
@Resolver(Skill)
export class SkillResolver {
  @Query(() => [Skill])
  async getAllSkills(): Promise<Skill[]> {
    const allSkills = await dataSource.getRepository(Skill).find();
    return allSkills;
  }
  // ...
}
```

### Utilisation dans un projet ✔️

[Wilders Book (frontend et backend](https://github.com/witzkvn/20221020_wildersbook_docker)

Description : Projet fullstack React et Node avec typescript et GraphQL, avec un CRUD sur la création de Wilders (Users).

### Utilisation en production si applicable❌ / ✔️

[lien du projet](...)

Description :

### Utilisation en environement professionnel ❌ / ✔️

Description :

## 🌐 J'utilise des ressources

### GraphQL doc

- https://graphql.org/learn/
- Documentation officielle de GraphQL

### Apollo GraphQL

- https://www.apollographql.com/docs/
- Apollo qui permet de simplifier grandement l'utilisation de GraphQL (sandbox en backend, et Apollo Client en frontend)

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
