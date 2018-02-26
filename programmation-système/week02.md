---
title: "Programmation orientée Système - Semaine 2"
author: [Florian Cassayre]
date: 2018-02-26
tags: [programmation-systeme]
...

### Stuctures de contrôle, blocs et portée

Les structures de contrôle s'écrivent et se comportent de la même manière qu'en Java (`if`, `switch`, `while`, `for`).

Seule différent : en C on peut déclarer des variables de même nom mais avec une portée différente. En cas d'ambiguité de nom, c'est la variable au bloc le plus proche qui est utilisée (résolution à la portée la plus proche).

Exemple :

```C
#include <stdio.h>

int const MAX = 5;
int main(void) {
  int i = 120;
  {
    int i = 1;
    for (; i < MAX; ++i) {
      printf("%d ", i);
    }
  }
  printf("%d\n", i);
  return 0;
}
```

Afficherait `1 2 3 4 120`.


Les variables déclarées en dehors de tout bloc sont appelées **variables globales** et sont accessibles dans tout le programme. Rappel : leur utilisation est fortement déconseillée. Seule exception, les variables globales _constantes_.

Proscrire l'utilisation des mots-clé `goto`, `break` (excepté dans les blocs `switch`) et `continue`.

### Les fonctions


#### Prototypage

Le prototypage consiste à déclarer la signature de la fonction sans déclarer le corps.
On définit le **nom** de la fonction, le **type de ses arguments** et le **type de sa valeur de retour**. Il est possible mais pas nécessaire de définir le nom des arguments.

**Toute** fonction déclarée doit avoir été préalablement prototypée avant d'être utilisée :

```C
double f(double);

double f(double x) {
  // ...
}
```

#### Fonctions sans arguments

Une fonction sans arguments se note avec le mot-clé `void` entre parenthèses :

```C
int main(void) {

}
```

#### Passage des arguments

Il existe deux paradigmes :

- Passage par valeur (C)
- Passage par référence (Java)

Il n'y a pas de passage par référence en C (les valeurs sont copiées par défaut). Toutefois il est possible de simuler ce comportement à l'aide des pointeurs :

```C
void f(int* x) { // Passage par référence
  *x = *x + 1;
  printf("x=%d", *x) // x=2
}

int main(void) {
  int val = 1;
  f(&val);
  printf(" val=%d\n", val); // val=2
  return 0;
}
```
