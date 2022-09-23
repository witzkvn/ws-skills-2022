# Titre de la compétence

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- l'état (_state_) pour contrôler l'affichage d'un composant ✔️
  En utilisant les states dans le JSX, celui-ci sera automatiquement re-rendu aux modifications des states.
- les composants enfants et les _props_ qu'on leur passe ✔️
  Les composants enfants sont des composants à l'intérieur d'un autre composant. On peut leur passer des props pour leur donner accès à certaines propriétés / fonctions venant du parent.
- le déclenchement d'instructions en fonction des actions de l'utilisateur ✔️ il existe des attributs à placer dans le JSX pour déclencer des appels vers des fonctions. Ces attributs sont par exemple : `onSubmit={fnToCall}` ou `onClick={fnToCall}`
- le déclenchement d'instructions en fonction de l'étape du cycle de vie du composant ou du changement de valeur de ses props ✔️
  On peut utiliser le hook `useEffect()` qui prend en premier paramètre une fonction (pour exécuter des instructions) et en deuxième paramètre un tableau de dépendance. Ces instructions vont s'exécuter à chaque modification de ces dépendances (un state par exemple). Si le tableau est vide, les instructions ne s'exécuteront qu'une seule fois au moment du rendu du component.
- l'usage d'un reducer (_useReducer_) pour gérer un état composé dans un composant ✔️ Lorsque l'on travail avec un state complexe (valeurs imbriquées, manipulations à faire sur les données...) il est préférable d'utiliser un reducer pour dispatcher des actions. La gestion du state peut alors être dissociée du component et gérer de nombreuses actions différentes dans un switch().
- l'état stocké dans un composant avec un _context provider_ et accessible dans ses descendants via `useContext` ✔️
  On peut créer un objet et le rendre accessible à un component et tous des enfants en créant un contexte (React.createContext(data)), puis on englobant les components nécessitant ce contexte entre des balise (context_name).Provider :
  ```jsx
  const ThemeContext = React.createContext(data);
  function App() {
    return (
      <ThemeContext.Provider value={data}>
        <Toolbar />
      </ThemeContext.Provider>
    );
  }
  ```
  Ici "Toolbar" et tous ses components enfant ont accès aux données dans le contexte ThemeContext (utiliser le hook useContext pour récupérer les valeurs dans un component enfant).

## 💻 J'utilise

### Un exemple personnel commenté ✔️

Exemple d'un component user-list.jsx qui permet de récupérer une liste de user et de l'afficher. On y trouve la gestion d'un loading et d'erreur.

```jsx
import React, { useState, useEffect, useCallback } from "react";
import UserCard from "./user-card";
import styles from "./user.module.css";

const UserList = () => {
  const [isLoading, setIsLoading] = useState(false);
  const [error, setError] = useState(false);
  const [users, setUsers] = useState([]);

  // empêche de re-générer la fonction à chaque render et donc de changer la référence à fetchUsers, ce qui relancerait le useEffect
  const fetchUsers = useCallback(async (fetchUrl) => {
    console.log("new function render");
    setError(null);
    try {
      const res = await fetch(fetchUrl);
      const data = await res.json();
      setUsers(data);
    } catch (error) {
      setError(true);
    }
    setIsLoading(false);
  }, []);

  // appel du useEffect au premier render, la fonction fetchUser ne devant pas changer
  useEffect(() => {
    setIsLoading(true);
    // ajout volontaire de 3 secondes pour voir le loading, à supprimer dans un cas réel
    const myTimeout = setTimeout(
      () =>
        fetchUsers("https://jsonplaceholder.typicode.com/users").then(() =>
          setIsLoading(false)
        ),
      3000
    );

    // suppression du timeout au demount du component
    return () => {
      clearTimeout(myTimeout);
      setUsers([]);
    };
  }, [fetchUsers]);

  // gestion affichage en cas d'erreur
  if (error) {
    return (
      <p>Une erreur est survenue lors de la récupération des utilisateurs...</p>
    );
  }

  // gestion affichage du loading : UserCard sans props, affichage spécial avec du CSS pour un état de chargement visuel dans ce component
  if (isLoading) {
    return (
      <div className={styles.userGrid}>
        <UserCard />
        <UserCard />
        <UserCard />
        <UserCard />
        <UserCard />
        <UserCard />
        <UserCard />
        <UserCard />
        <UserCard />
      </div>
    );
  }

  // gestion du cas de succès mais aucun user trouvé
  if (!isLoading && users.length === 0) {
    return <p>Aucun utilisateur n'a été trouvé.</p>;
  }

  // gestion du cas de succès et affichage des users trouvés
  return (
    <div className={styles.userGrid}>
      {users && users.map((user) => <UserCard key={user.id} user={user} />)}
    </div>
  );
};

export default UserList;
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
