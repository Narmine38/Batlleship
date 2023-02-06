# Battleship - Projet Vue.JS

Un jeu de bataille navale à développer avec Vue.JS.

![](images/header.jpg)

Ce projet a pour objectif de permettre l’acquisition de compétences avancées en Vue.js. Il s'intègre au modules **Javascript** et **SPA** et permet l'acquisition des compétences complémentaires.

➡️ Faites d'abord un point sur les compétences qui vous manquent sur le module socle.

## Consignes

Programmer **un jeu de bataille navale en multijoueur**, sur un seul ordinateur.

Chaque joueur possède une flotte composée de 5 bateaux, qui sont les suivants : 1 porte-avion (5 cases), 1 croiseur (4 cases), 1 contre torpilleur (3 cases), 1 sous-marin (3 cases), 1 torpilleur (2 cases).
Le plateau de jeu est une grille de 10 x 10 cases.

**Dans une première phase de jeu** : les joueurs positionnent leur bateaux sur le plateau de jeu.

**Dans une seconde phase de jeu** : les joueurs s'attaquent en tirant sur la grille de l'adversaire pour trouver ses bateaux.

Le but est de couler les bateaux adverses, c'est à dire de trouver toutes les cases occupées par la flotte ennemie.

—

‼️ Ce document décrit les attentes **fonctionnelles** autour de ce projet.

**Il n’a pas vocation à être exhaustif et les fonctionnalités décrites dans ce document peuvent être complétées à votre guise.**

## ⚠️ Modalités de rendu ⚠️

Votre avancement devra être présenté dans des commits, sous la forme suivante :

- Une Pull Request minimum par exercice, avec un message reprenant l'intitulé de l'exercice.
- Chaque Pull Request contient les modifications de code **et** une modification du sujet pour renseigner l'avancement.

Exemple pour le [premier exercice](#mettre-en-place-son-repo-git) :

<img width="956" alt="git-commit" src="https://user-images.githubusercontent.com/632197/42737442-a94e7534-8873-11e8-82fa-75d178493074.png">

_Les fichiers readme sont [au format Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet). Pour chaque exercice que vous compléterez, cochez la case dans le sujet en rajoutant une croix._

### Comment s'organiser ?

Vous travaillerez sur une branche par fonctionnalité, en respectant le [Workflow de branche par fonctionnalité](https://www.smartwavesa.com/blog-articles/git-quelle-strategie-de-branching/).

- Tous les commits doivent être faits sur une branche dédiée à la fonctionnalité, par ex. `create-grid`, `handle-placement-errors`, `attack-animations`, `ships-images` ...
- Une fois poussés, les commits doivent être présentés dans une Pull Request.
- Chaque Pull Request doit être lue et validée, puis mergée par un **autre membre** de votre ilôt.

### Pense bête :

À chaque début de fonctionnalité, il faudra donc :

- Récupérer les modifications depuis `master` distant
- Ouvrir un nouvelle branche depuis `master` local
- Travailler sur cette branche, committer.

À chaque fin de fonctionnalité :

- Récupérer les modifications depuis `master` distant
- Pousser votre branche
- Ouvrir une Pull Request vers `master` ( en restant bien sur votre repo Git )
- Informer votre îlot que vous avez besoin de leur relecture !

## Itération 0 : Préparation du projet

### Mettre en place son repo Git

- [ ] Forkez ce repo, et clonez votre fork
- [ ] Créez une branche `mise-en-place-git` depuis `master`.
- [ ] [Commitez la complétion](https://user-images.githubusercontent.com/632197/42737442-a94e7534-8873-11e8-82fa-75d178493074.png) des 3 étapes de cet exercice sur `mise-en-place-git`, puis ouvrez une Pull Request vers `master` sur votre repo.

_Pour cela, dans un git bash :_

```bash
git clone <URL_DE_VOTRE_FORK>
# Choisir url https, ou ssh si vous avez un clé ssh configurée sur votre machine
cd <NOM_DU_DOSSIER>

# ajouter mon repo comme remote supplémentaire
git remote add campus git@github.com:le-campus-numerique/JS_vue-battleship.git
# ou https://github.com/le-campus-numerique/JS_vue-battleship.git en HTTPS

# pour vérifier mes remotes
git remote -v

# pour récupérer les modifications depuis chez le campus
git pull campus master
```

_Pour voir en local ce que les collègues ont fait, on peut les ajouter aussi comme remote supplémentaires_

```bash
# ajouter collègue comme remote supplémenaire
git remote add collegue git@github.com:collegue/JS_vue-battleship.git

# télécharger les modification du projet du collègue
git fetch collegue

# pour voir le contenu de sa branche super-feature
git branch super-feature collegue/super-feature
```

### Étudier les règles du jeu

**Avant de se mettre à coder, il faut bien réfléchir aux règles du jeu et aux algorithmes.**

Au cas où... [les règles sur wikipedia](<https://fr.wikipedia.org/wiki/Bataille_navale_(jeu)>)

- [ ] Comprendre les règles du jeu et formuler le plus précisément possible les mécanismes de l'application que vous allez développer.
      _Présentez ici votre application telle que vous l'imaginez, avant de la développer. Dans une second temps, vous pourrez lister précisément ce qui fonctionne vraiment._

**Algorithme du jeu :**

! Etape importante !

Se poser des questions de type "comment, combien, quoi, qui" et y répondre. Par exemple : Combien de joueurs ? Comment stocker les bateaux ? Comment stocker les tirs ? Comment matérialiser les grilles ? Combien de grilles ? Comment fonctionnent les scores ? etc...

[Complétez ici]

### Définir les tâches à réaliser

- [ ] Créer un Github project contenant un [board](https://docs.github.com/en/issues/organizing-your-work-with-project-boards/managing-project-boards/about-project-boards)

## Itération 1 : Déploiement de la flotte.

Le joueur A et le joueur B vont placer leurs bateaux chacun leur tour.

- [ ] Initialisez une application `Vue.js` dans ce repo.
- [ ] Ajouter au `README.me` (ce fichier) les informations nécessaires pour utiliser votre projet.

### Créer l'interface de jeu

Ajoutez dans votre application :

- [ ] Une grille de taille fixe (10x10), le plateau de jeu.
- [ ] Un listing de vos bateaux
- [ ] Une zone pour afficher les messages

### Ajouter un formulaire qui permet de positionner ses bateaux sur la grille en début de partie (d'abord le joueur A, puis le joueur B)

- [ ] Chaque bateau peut être positionné sur la grille en rentrant des coordonnées dans un formulaire
- [ ] Chaque bateau peut être disposé à l'horizontale ou à la verticale
- [ ] Les bateaux ne peuvent pas dépasser de la grille, se superposer, ou être posés plusieurs fois.
- [ ] On peut vider la grille pour recommencer le placement

### Afficher les succès et erreurs, et états - visuellement ou avec du texte

- [ ] Afficher les retours nécessaires lors de cette étape de placement de la flotte.

## Itération 2 : Attaque entre deux joueurs.

### Attaque de l'adversaire

- [ ] Le joueur actif ne voit pas la grille de jeu de l'autre
- [ ] Chaque joueur joue à son tour
- [ ] La grille présente les cases déja jouées pour chacun
- [ ] On affiche un retour suite à l'attaque. Touché, coulé ...
- [ ] Ajouter des animations aux attaques

### Scores

- [ ] Afficher les scores au cours de la partie
- [ ] Ajouter une page dédiée aux scores des parties précédentes

### Le joueur a ses faiblesses

- [ ] Un joueur peut annuler un coup, ou plusieurs : gérer l'historique des coups
- [ ] Si la page est rechargée, on peut reprendre la partie en cours : gérer la persistance des données

## Itération 3

### Presque de l'IA

- [ ] Une option permet de positionner les bateaux sur la grille de façon aléatoire en début de partie

### Bataille TV

- [ ] On peut voir un replay de la partie complète

## Déploiement : publier l'application

### Génération du projet en local

Vous avez plusieurs commandes disponibles dans votre projet Node.
Depuis la racine du projet, lancez la commande `build`

```bash
  npm run build
```

Cela va générer un build de notre application, dans le dossier `dist`.
Le contenu de ce dossier est un projet HTML, CSS et JS, prêt à être rendu sur n'importe quel navigateur.
Ce sont donc ces fichiers que l'on va placer sur un serveur.

Pour tester cela, lancez un simple serveur local dans `dist` :

```bash
  cd dist
  http-server
```

### Mise en ligne

Votre code source est hébergé sur GitHub. GitHub propose également d'héberger des sites statiques et met à notre disposition une url par repo avec [Github Pages](https://pages.github.com/)

Nous allons utiliser Github Pages pour servir la version compilée de notre projet. Pour cela, il va nous falloir publier une branche qui contient le projet buildé, donc le contenu du dossier `dist`.

En local, on peut créer une commande qui fait ce travail pour nous.

- Suivez ce tutoriel pour créer ce script, en l'adaptant avec vos infos de repo.
  https://cli.vuejs.org/guide/deployment.html#github-pages

- Lancez ce script en ligne de commande, ou via un script npm.

- Poussez votre nouvelle branche `gh-pages` avec son contenu.

Depuis votre repo sur GitHub :

- Configurez Pages depuis Settings > Pages
- 
- Choisissez comme "source" la branche `gh-pages`

Votre projet sera disponible à l'adresse indiquée.

# Ressources

Ressources :

- [The Vue Handbook](Vue_Handbook.pdf)
- [The Vue Cheat Sheet](Vue.js_Cheat_Sheet.pdf)

Flux & Gestion de State

- https://medium.com/hacking-and-gonzo/flux-vs-mvc-design-patterns-57b28c0f71b7
- https://vuex.vuejs.org/


# Compétences

Liste des compétences et indications pour les intégrer à votre projet.

Obligatoires

- Utiliser un builder type webpack : à intégrer dans votre projet en général
- Différencier Computed vs Watched properties : dans la gestion de vos data, cherchez celles qui pourraient tirer parti de ces mécanismes
- Mettre en place une gestion de State centralisée : utiliser un store pour le partage des datas communes dans vos composants/view, actions communes à géneraliser (grille, bateaux, score, coups, etc)
- Connaitre les étapes du cycle de vie en Vue : utiliser mounted et created
- Stocker l'état de son application dans le navigateur avec LocalStorage : persistance des datas du jeux (grille, bateaux, score, coups, etc)
- Utiliser un preprocesseur CSS : à intégrer dans votre projet en général
- Faire des filtres en Vue.js : sur les scores, les affichages divers de temps, etc.

Optionnelles

- Intégrer un design system avec des composants : voir avec un formateur
- Développer une version statique de l'application
- Mettre en place de l'infinite scrolling : par exemple sur le liste des coups
- Animer des composants
- Tester un composant : utiliser les fonctionnalités de test unitaire sur certaines methodes principales de votre app
- Rendre l'application multilingue
