---
title: "Programmation orientée Système - Semaine 1"
author: [Florian Cassayre]
date: 2018-02-19
tags: [programmation-systeme]
...

### Comparaison avec Java

[]() | **C** | **Java**
---: | :---: | :---:
**Langage** | Impératif | Orienté objet
**Code objet** | Code machine | Byte code
**Vérification à la compilation** | Faible | Forte
**Allocation mémoire** | Statique et dynamique | Dynamique
**Manipulation directe de la mémoire** | Oui | Non
**Vérification des accès mémoire** | Non | Oui
**Désallocation** | Manuelle | Automatique

### Structure générale

```C
#include <nom_du_paquet>
// ...

// Déclaration d'objets globaux (à éviter !)

// Déclarations des fonctions

int main(void) {

  // Corps du programme principal (si possible court)

  return 0;
}

```

### L'opérateur =

En C, il **modifie** le contenu de son premier opérande (à gauche).

En Java, cela ne fait que **créer une référence** de plus sur son second opérande (celui
de droite).


### Remarques importantes

- La syntaxe ressemble à Java _cependant_ ce cours insistera sur les nombreux aspects qui en diffèrent
- Les données sont clairement séparées des traitements
- Aucune notion d'orienté-objet, pas d'encapsulation, ni héritage, ni polymorphisme
- Ne pas déclarer de variables globales, à moins d'avoir une bonne raison de le faire
- Il n'y a pas de chaînes de caractères, utiliser `char[]` à la place
- Il n'y a pas de booléen (du moins en C89), utiliser un `int` à la place
- Toujours initialiser les variables avant utilisation

_De plus..._

Toute valeur peut être traduite en un booléen. Une valeur nulle (`0`, `0.0`, ...) est fausse, le reste est vrai. L'utilisation de cette fonctionnalité est toutefois déconseillée.

Toute opération retourne une valeur. Ainsi, écrire `x = 3` au lieu de `x == 3` retournerait `3` qui est une valeur vraie. Il est conseillé d'inverser les opérandes pour générer une erreur de compilation en cas d'erreur.

Il existe l'opérateur binaire `,`... Conseil : ne pas l'utiliser !

### Normes

Il existe plusieurs normes : `C89`, `C99` et `C11`.

Pour ce cours il est recommandé d'utiliser `C99`, cela se spécifie au compilateur : `gcc -std=c99`
