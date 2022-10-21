# TypeScript

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- l'intéret de TypeScript dans l'IDE ✔️

  Permet d'ajouter un typage fort sur les variables, afin de détecter les erreurs de compilation et de faciliter le débuggage

- les types de bases ✔️

  number, string, boolean. On a ensuite les arrays d'un type (ex: number[]), les enum, les tuples...

- comment et pourquoi étendre une interface ✔️

  Etendre une interface permet d'implémenter l'interface étendue (récupérer ses propriétés et ses méthodes) dans une nouvelle interface. Dans l'exemple ci-dessous, si MyInterfaceA venait à changer, alors MyInterfaceB serait automatiquement changée aussi !

```typescript
interface MyInterfaceB extends MyInterfaceA {
    // get all properties and methods from MyInterfaceA, and add new ones
    myNewProp: number,
    myNewMeth(myParam: string) => string
}
```

- les classes et les decorators ✔️

  Les classes permettent de décrire une entité, un peu comme un plan de construction. Elle contient un constructor qui est la fonction appelée lors de l'instanciation de cette classe, des propriétés et des méthodes.
  Les decorators se placent au-dessus des propriétés / méthodes et permettent d'ajouter des informations. Ils s'écrivent avec "@\<nom decorator\>". Un exemple de decorator utilisés avec typeorm sur une classe entité :

  ```javascript
  @Entity()
  export class Wilder implements IWilder {
    @PrimaryGeneratedColumn()
    id: number;

    @Column()
    name: string;

    @Column()
    city: string;

    @Column()
    description: string;

    @Column()
    avatar?: string;

    @OneToMany(() => Grade, (grade) => grade.wilder, {
      cascade: true,
    })
    grades: Grade[];
  }
  ```

## 💻 J'utilise

### Un exemple personnel commenté ✔️

Exercise from exercism.io to get a resistor value depending on the colors on it

```typescript
export function decodedResistorValue(colors: string[]): string {
  const codes: { [key: string]: string } = {
    black: "0",
    brown: "1",
    red: "2",
    orange: "3",
    yellow: "4",
    green: "5",
    blue: "6",
    violet: "7",
    grey: "8",
    white: "9",
  };

  // get first two numbers
  const selectedColors = colors.slice(0, 2);
  const firstTwoValues = selectedColors.reduce(
    (acc, current) => acc + codes[current],
    ""
  );

  // get third color and set all 0
  let nbOfZeros = parseInt(codes[colors[2]]) || 0;
  let zerosString = "";
  for (let i = 1; i <= nbOfZeros; i++) {
    zerosString += "0";
  }

  // create whole number
  let resNumber = parseInt(firstTwoValues + zerosString);

  // check if more than 1000 to convert in kiloohms
  let unit = "ohms";
  if (resNumber > 1000) {
    unit = "kiloohms";
    resNumber = resNumber / 1000;
  }

  return `${resNumber} ${unit}`;
}
```

### Utilisation dans un projet ✔️

[Wilders Book Typescript Backend](https://github.com/witzkvn/20220920_wilders_book_ts_backend)

Description : Projet backend Wilders Book API REST en typescript

### Utilisation en production si applicable❌ / ✔️

[lien du projet](...)

Description :

### Utilisation en environement professionnel ❌ / ✔️

Description :

## 🌐 J'utilise des ressources

### Typescript doc

- https://www.typescriptlang.org/docs/handbook/intro.html
- Handbook typescript qui décrit en détail beaucoup de notions TS

### Exercism.io

- https://exercism.org/tracks/typescript
- Exercices TS

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
