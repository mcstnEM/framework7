# Introduction

Objectif de ce cours interactif :

- Découvrir JavaScript dans le contexte d'une page Web afin de découvrir le DOM, les événements et quelques notions importantes du langage : définition de variables, première approche, boucle, type des données et gestion des chaînes de caractères.

On dit JS pour dire JavaScript. 

Essentiellement pour nous dans nos métiers Full-Stack il sera utilisé dans les cas suivants :

- Il peut s'appliquer à un document HTML côté client, de manière simple avec un script JS lié à une page HTML, pour gérer les interactions utilisateurs et rafraichir le DOM (Document Objet Model).

- Il peut servir à développer des API application programming interface, donc des applications côtés serveurs avec NodeJS.

- Il sert à développer des applications front-end très techniques, avec React ou Angular par exemples. Les applications front-end s'exécute dans le navigateur lui-même. Donc côté client, ce sont des interfaces utilisateurs.


## DOM

Document Object Model est une interface de programmation, elle représente le HTML de votre page Web et permet d'accéder aux éléments HTML de cette page à l'aide de JS. Pour par exemple modifier certains de ces éléments.

Le DOM est un arbre avec un élément racine : la balise html, elle a pour enfant : head, body.

Nous pourrons en JS faire les actions suivantes sur les éléments du DOM :

- Modifier du contenu précis dans un élément spécifique du DOM.

- Modifier le style d'un élément.

- Créer ou supprimer un élément.

- Capturer ou écouter les interactions de l'utilisateurs et faire quelque chose d'intelligent en fonction de ces actions.

- ...En pleins d'autres choses.

Mais nous verrons que tout commence avec un objet JS particulier **document**. Voyez le comme le point d'entré de la page Web pour accéder aux éléments HTML (aux noeuds de l'arbre du document HTML.

Créez un dossier sur votre serveur localhost "JavaScript_introduction" pour les exercices suivants :

## Exercice 01 liste de nombres 

Récupérez le dossier **projet_01_list_numbers_start** dans les sources.

1. Utilisez **querySelectorAll** méthode de l'interface **Document** permettant de cibler des éléments du DOM à l'aide d'une règle CSS à trouver. Puis dans la partie script de la page index.html faites un console.log pour afficher ces éléments, vous devriez voir nos ul/li :

```js
let els = document.querySelectorAll(Votre_regles_css);
console.log(els)
```

Remarques : un **console.log** permet d'afficher un résultat dans l'inspecteur de votre navigateur. Faites un click droit sur votre navigateur puis Inspecter et enfin sélectionner "Console" dans la fenêtre de l'inspecteur.

2. En utilisant maintenant querySelector qui permet de cibler un élément dans le DOM et innerHTML qui permet de modifier le contenu d'un élément HTML, permutez les valeurs A, B et C, attention chaque valeur se trouve dans un sous-élément span. N'utilisez pas de boucle pour l'instant pour répondre à cette question.

```txt
A = 3
B = 1
C = 2
```

*Remarque :* 

- Aidez-vous du code suivant pour modifier la valeur du span :

```js
element.querySelector('span').innerHTML = 2
```

- Pour accéder à une valeur d'un array en JS vous utiliserez la syntaxe suivante :

```js
let myArray = [1, 2, 3];

myArray[0]; // 1
myArray[1]; // 2
myArray[2]; // 3
```

3. Vous allez maintenant utiliser une boucle JS pour faire la même chose, permuter les valeurs A, B et C, ici on souhaite automatiser l'assignation dans la permutation. Utilisez également la méthode length qui permet de calculer la longueur d'un tableau.

```js
// Boucles JS
for(let i = 0; i < 3; i++){
    console.log(i);
}

// Calculer la longueur d'un tableau
myArray.length
```

## Exercice 02 Créer...

Récupérez le dossier **projet_02_create_start** dans les sources.

Nous allons maintenant créer des éléments dans le DOM. La méthode createElement permet de créer un élément dans le DOM :

```js
let li = document.createElement('li');
```

Pour sélectionner un élément du DOM on peut également utiliser un **getElementById** qui cible un identifiant d'une balise :

```js
let container = document.getElementById('numbers');
```

Puis, avec la fonction **appendChild** on ajoute l'élément à ce noeud, l'élément créé se placera à la suite des autres éléments li :

```js
container.appendChild(li);
```

Créez 5 autres à la suite des trois premiers éléments (voir le fichier source pour commencer) en respectant l'ordre alphabétique et en incrémentant de +1 chacune des valeurs :

```txt
A=1
B=2
C=3
D=4
E=5
F=6
G=7
H=8
```

## Exercice 03 nombre de caractères (écouter un événement)

Récupérez le dossier **projet_03_number_char_start** dans les sources.


Nous allons créer un formulaire pour saisir une phrase, puis une fois que l'on aura cliqué sur le bouton "Calculer" nous afficherons le nombre de particules(s) saisie(s).

Ecoutez un événement ... Utilisez le code suivant pour écouter les changements sur l'élément input du formulaire :

```js
let elInput = document.querySelector('.phrase');

// une fonction dite de callback que l'on passera à addEventListener
function eventInput(event){
    let value = event.target.value;

    console.log(value);
}

// On écoute les changement des inputs dans l'élément input
elInput.addEventListener('input', eventInput);
```

1. Affichez en temps réel le nombre de caractères dans la balise result.

2. Lorsqu'on clique sur Calculer affichez maintenant le nombre de particule(s) que l'on a saisi dans le champ input. Utilisez le code source de l'exercice.

*Les questions suivantes sont facultatives.*

3. Gérez le cas où l'utilisateur saisi une chaîne de caractères vide et qu'il clique sur "Calculer". Affichez dans ce cas un message d'erreur.

4. L'utilisateur peut saisir des particules et introduire des espaces, ce qui fausse le calcul du nombre de particule. Trouvez une solution pour nettoyez le chaîne saisie afin de compter le bon nombre de particule(s).

Remarques pour cette dernière question, on peut evisager un nettoyage encore plus "fin", mais cela reste une question ouverte, il nous manque des notions... Vous pourriez par exemple vérifiez que chaque caractère de chaque particule est bien un caractère alphabétique ...