# Langage Javascript

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les `structures` de base du langage ✔️
  Javascript est un langage de script ayant plusieurs types primitifs (number, string, bool, null, undefined...) et non primitifs (object).
- les normes `ecmascript` ✔️
  Ensemble de normes disponibles sur le site [ECMA INTERNATIONAL](https://www.ecma-international.org/) qui définissent les standards du langage Javascript (par exemple les fonction existantes sur les objets Dates, et comment elles fonctionnent)
- l'utilisation de l'`asynchrone` ✔️
  Du code asynchrone est du code dont on ne sait pas à l'avance le temps d'exécution. On peut le gérer avec .then() et .catch() ou en utilisant un block trycatch avec async / await.
- les spécifités du mot-clef `this` ✔️
  this fait référence à l'objet dans lequel le code est exécuté. Par exemple dans une classe, this fera référence à l'instance de cette classe.

## 💻 Je code en Javascript

### Un exemple de code commenté ✔️

Exemple d'un [codewar](https://www.codewars.com/kata/52742f58faf5485cae000b9a) : Human Readable duration format

```javascript
function formatDuration(seconds) {
  // if 0 seconds, it means now
  if (seconds === 0) return "now";

  // else, we set constant durations to simplify the code then
  const minuteInSeconds = 60;
  const hourInSeconds = 60 * minuteInSeconds;
  const dayInSeconds = 24 * hourInSeconds;
  const yearInSeconds = 365 * dayInSeconds;

  // the rest variable always contains seconds that are not yet converted in the process
  let rest = seconds;
  let years, days, hours, minutes;

  // from bigger to smaller, count years, days, hours and minutes. Variable rest will then contain the remaining seconds
  [years, rest] = getCountAndRestFor(yearInSeconds, rest);
  [days, rest] = getCountAndRestFor(dayInSeconds, rest);
  [hours, rest] = getCountAndRestFor(hourInSeconds, rest);
  [minutes, rest] = getCountAndRestFor(minuteInSeconds, rest);

  // formatting the response string
  let strArr = [
    years > 0 ? formatStrPortion(years, "year") : null,
    days > 0 ? formatStrPortion(days, "day") : null,
    hours > 0 ? formatStrPortion(hours, "hour") : null,
    minutes > 0 ? formatStrPortion(minutes, "minute") : null,
    rest > 0 ? formatStrPortion(rest, "second") : null,
  ];
  strArr = strArr.filter((el) => el !== null);
  let str = strArr.join(", ");

  const lastIndex = str.lastIndexOf(", ");
  const replacement = " and";

  // return formatted response
  if (lastIndex > -1) {
    // the last portion must be linked with the sentence by 'and' word
    return `${str.substring(0, lastIndex)}${replacement}${str.substring(
      lastIndex + 1
    )}`;
  } else {
    return str;
  }
}

// returns the value in the unit demanded (year, minutes...) and the extra seconds
function getCountAndRestFor(unitValueForDurationInSeconds, seconds) {
  unitValue = Math.floor(seconds / unitValueForDurationInSeconds);
  rest = seconds % unitValueForDurationInSeconds;
  return [unitValue, rest];
}

// returns the formatted string to form the response
function formatStrPortion(value, unit) {
  if (value > 1) {
    return `${value} ${unit}s`;
  } else if (value === 1) {
    return `${value} ${unit}`;
  } else {
    return "";
  }
}
```

### Utilisation dans un projet ❌ / ✔️

[lien github](...)

Description :

### J'ai utilisé ce langage en production ❌ / ✔️

[lien du projet](...)

Description :

### J'ai utilisé ce langage en environement professionnel ❌ / ✔️

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
