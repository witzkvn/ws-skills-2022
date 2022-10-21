# Période en entreprise du 19/09/2022 au 14/10/2022

> Répond aux questions suivantes afin de préparer le partage d'expérience avec ton groupe

## Intégration

1. S'agit il de tes premiers jours dans l'entreprise ? (Si non, précise la date d'entrée)

   Je suis entré dans l'entreprise une semaine avant la rentrée officielle, le 05 septembre 2022. Cela m'a permis de faire une semaine d'intégration avant la reprise des cours.

2. Décris comment se déroule la communication avec ton tuteur. (fréquence, valeur de l'aide ajoutée)

   Nos bureaux sont accolés, nous pouvons communiquer facilement et rapidement, dès que besoin. Il est toujours disponible lorsque j'ai besoin de son avis ou de son expertise.

3. Décris ta mission actuelle au sein de l'entreprise

   Je suis seul en charge de créer le Backend de la nouvelle plateforme web de l'entreprise. Son but est de proposer l'accès à nos outils RH (déjà existants) à nos clients, sur notre propre plateforme (actuellement les outils sont disponibles sur des plateformes de partenaires).
   La plateforme doit donc permettre à des utilisateurs de créer un compte, se connecter, créer des magasins, créer des offres d'emploi, accéder aux outils d'IA disponibles, gérer les candidats...

4. Qu'est ce qui a bien fonctionné en terme de communication avec ton équipe ?

   L'équipe de dev étant petite (3 personnes), la communication est très facile. Il est possible d'improviser des réunions en dernière minute si besoin.

5. Qu'est ce qui n'a pas bien fonctionné en terme de communication avec le reste de l'équipe ?

   Le développeur frontend étant aussi alternant, mais pas avec le même rythme, nous ne nous croisons pas régulièrement. Notre travail étant étroitement lié, cela peut parfois être un frein dans l'avancée du projet.

6. Quelle(s) proposition(s) pourrais tu faire pour améliorer ton intégration dans l'équipe ?

   RAS.

## Expérience technique

1. Quel est le projet principal sur lequel tu as travaillé sur cette période. (liste les projets si il y en a plusieurs) ?

   J'ai mis en place le backend avec pour le moment la gestion de l'authentification des utilisateurs qui me semblait être prioritaire. Le projet est en Node / Express / Typescript / MongoDB.

2. Quelle est la tâche la plus intéressante accomplie lors de cette période ?

   J'ai mis en place des tests avec JEST, et créé de nombreuses fonctions utilitaires pour simplifier et factoriser le tout. Cela a pris beaucoup de temps, mais dorénavant l'écriture de tests est simple et rapide.

3. Ta plus grosse réussite ?

   En dehors de l'écriture des tests mentionnés ci-dessus, la mise en place du backend selon mes envie (seul responsable du backend, j'ai pu choisir ma stack technique et l'architecture du projet).

4. La plus grosse difficulté (echec ou perte de temps) ?

   J'ai essayé de mettre en place un système de logs. J'y arrive en les écrivant dans des fichiers locaux JSON. Mais j'ai ensuite voulu configurer un système Elasticsearch / Kibana pour y visualiser les logs, le tout sur notre serveur de production. Mais impossible de réussir à envoyer les logs de mon back vers mon EK. Maintenant que l'on a vu docker en cours, je pourrai retenter avec une image docker pour éviter toutes les configurations manuelles.

5. Quel langage as tu le plus utilisé ?

   Du typescript.

6. Quel design pattern as tu pu identifier ?

   Pour l'instant aucun spécifique.

7. Sur quel point ton formateur ou ton groupe peuvent ils t'aider ?

   Mise en place du système ELK pour les logs sur un serveur distant et lié avec mon backend présent dans un projet Back + Front Dockerizé, mais cela est plus proche du devops que du dev backend.
