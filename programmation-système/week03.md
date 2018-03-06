---
title: "Programmation orientée Système - Semaine 3"
author: [Florian Cassayre]
date: 2018-03-05
tags: [programmation-systeme]
...

## Types de données avancés

### Types élémentaires

On peut rajouter un modificateur devant la déclaration des variables afin de changer l'interprétation et le nombre de bits d'encodage :

- `long int name;`
- `short int name;`
- `unsigned int name;`

Depuis C99 il existe également :

- `long long int`
- `double complex` et `double imaginary`
- `bool`
- `int8_t`, `unint8_t`, ..., `int64_t`, `unint64_t` (nombre de bits garanti)

Et un certain nombre de constantes définies dans `limits.h` et `float.h`.

### Enumérations

```C
enum CantonRomand {
  Vaud,
  Valais,
  Geneve,
  Neuchatel,
  Fribourg,
  Jura
}
```

En C les enum peuvent être interprétés comme des `int`.

### Tableaux

Les tableaux ne connaissent pas leur taille !

```C
int tableau[42];
```

Lorsque la taille initiale est constante, il est recommandé de la définir dans une constante :

```C
size_t const TAILLE = 42;
double tableau[TAILLE];
```

Pour représenter des tailles, utiliser le type `size_t` (il est garanti que ce soit un entier positif). Ainsi lorsque l'on veut itérer dans un tableau, ne pas utiliser `int`.

Ou bien à la compilation :

```C
#define TAILLE 42
double tableau[TAILLE];
```

Passage d'un tableau en argument :
```C
void f(double tableau[], size_t const taille)
```

_Note_ : `tableau[]` est complètement équivalent à `*tableau`.

_Attention_, il n'y a **pas de contrôle de débordement** sur les tableaux !

### Alias de types

Il est possible de définir un nouveau nom pour un type avec le mot clé `typedef` :

```C
typedef double Matrice[3][3];
```

### Structures

```C
struct Name {
  type1 name1;
  type2 name2;
  // ...
};

// Utilisation
struct Name name;
```

On utilise souvent la syntaxe suivante pour éviter d'avoir à utiliser le mot clé `struct` lors de l'utilisation :

```C
typedef struct {
  type1 name1;
  type2 name2;
  // ...
} Name;

// Utilisation
Name name;
```

Initialisation des structures :
```C
struct Name name;
(void)memset(0, 0);
```
