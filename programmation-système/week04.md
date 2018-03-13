---
title: "Programmation orientée Système - Semaine 4"
author: [Florian Cassayre]
date: 2018-03-12
tags: [programmation-systeme]
...

## Les entrées-sorties

### Affichage à l'écran

La fonction `printf` effectue la conversion lors de l'exécution. Elle retourne le nombre de caractères écrits ou `-1` en cas d'échec.

Pour voir toutes les possibilités de formattage, `man 3 printf`.

Afin de forcer l'affichage de stdout (= vider le tampon), appeler `fflush` (utiliser uniquement pour le déboguage).

### Lecture au clavier

Très similaires aux formats de `printf`, `scanf`.

En revanche, utiliser...

- `%lf` pour lire un `double`
- `%[...]` pour lire des chaînes de caractères (exemple, `%[A-Z]`, pour lire tous les caractères majuscules)
- `%*` pour un champ non affecté (peu utile)

#### Contrôle de l'entrée

La portion de code suivante produit une boucle infinie si on tape `'a'` par exemple :

```C
do {
  printf("Entrez un nombre entre 1 et 10 : ");
  fflush(stdout);
  scanf("%d", &i);
} while ((i < 1) || (i > 10));
```

Voici une solution à ce problème :

```C
do {
  printf("Entrez un nombre entre 1 et 10 : "); fflush(stdout);
  j = scanf("%d", &i);
  if (j != 1) {
    printf("Je vous ai demandé un nombre, pas du charabia !\n");
    /* vide le tampon d'entrée */
    while (!feof(stdin) && !ferror(stdin) && getc(stdin) != '\n');
  }
} while (!feof(stdin) && !ferror(stdin) && ((j!=1) || (i<1) || (i>10)));
```

Toutefois pour des entrées complexes on n'utilise plus `scanf`.

### Sortie erreur standard

Aussi envoyé vers le terminal, comme stdout, mais correspond bien à un flot séparé.

### Utilisation des fichiers

On manipule toujours des pointeurs de fichiers `FILE*`.

```C
FILE* fopen(const char* nom, const char* mode)
```

Si le fichier n'a pas pu être ouvert, la variable fichier est égale à `NULL`.

Ne pas oublier de fermer tout fichier ouvert !

```C
fclose(file);
```


#### Flots

`fprintf`, `fscanf` et `fprintf(stderr, ..., ...)`.
