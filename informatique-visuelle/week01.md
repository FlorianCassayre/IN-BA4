---
title: "Introduction à l'Informatique Visuelle - Semaine 1"
author: [Florian Cassayre]
date: 2018-02-20
tags: [informatique-visuelle]
...

## Vision Humaine

### L'oeil

#### Anatomie

L'oeil est un organe qui procure le sens de la vue. Il est constitué grossièrement des éléments suivants :

- La pupille : diaphragme qui régule la lumière entrant dans l'oeil
- Le cristallin : lentille convergente qui permet d'adapter l'image
- La rétine : organe sensible de la vision, contient des cônes et des bâtonnets
- La fovéa : partie centrale de la rétine peuplée uniquement de cônes

#### Les bâtonnets

Très sensibles à la lumière, ont une fréquence d'échantillonnage de 100 images par seconde, ils sont environ 130 millions et correspondent à des **niveaux de gris**.

#### Les cônes

Moins sensibles à la lumière, avec une fréquence d'échantillonnage de seulement quelques images par seconde, ils sont environ 6.5 millions et permettent la vision des **couleurs**.

On en distingue trois types qui permettent de voir les longueurs d'ondes correspondant au **bleu**, au **vert** et au **rouge**.

#### La vision périphérique

Seule la zone centrale possède une bonne acuité. Afin de "scanner" l'intégralité de l'espace qui l'entoure, l'oeil se déplace constamment. Ce mouvement se décompose en deux étapes :

- La **fixation** : l'oeil se pose, prélève l'information
- La **saccade** : l'oeil saute rapidement vers un autre point

Les bâtonnets permettent une vision périphérique sensible aux mouvements.

La vision périphérique est limitée par le point aveugle.

### La perception du mouvement : oeil ou cerveau ?

 **L'effet Stroop** : L'interférence que produit une information non pertinente au cours de l'exécution d'une tâche cognitive (nom de la couleur écrit dans une fonte de couleur différente).

**La persistence rétinienne** : l'image reste un certain temps dans le cerveau après avoir été vue. Cette hypothèse donnerait une explication physique à ce phénomène.

**Effet PHI et effet BETA** : percevoir des mouvements inexistants. Cette hypothèse à l'inverse démontre que c'est bien le cerveau qui crée la perception du mouvement.

De plus les connaissances déjà acquises jouent un rôle conséquent dans l'interprétation des images percues par l'oeil. Elles permettent de donner un contexte et faciliter la compréhension.

En conclusion l'oeil ne se charge que d'assimiler les informations, c'est au cerveau que revient le travail de traitement.

### Représentation de l'image

#### Facteurs de définition de l'écran

- Les dimensions : longueur de la diagonale (généralement en pouces)
- La définition : nombre de pixels au total
- La résolution : nombre de pixels par pouce carré (ppp ou dpi)
- Profondeur : nombre de bits par pixel

#### Compression de l'image

Taille de l'image $=$ Nombre de pixels $\times$ Profondeur du pixel $\times$ Taux de compression

On distingue deux modes de compression : sans perte (**lossless**) et avec perte (**lossy**). Dans la plupart des cas la compression avec perte ne produit pas d'anomalies visuelles significatives mais réduit sensiblement la taille du fichier.

#### Recréation de la profondeur

De nombreuses techniques sont utilisées, parmi celles-ci :

- La perspective
- L'occlusion
- La taille relative
- La position par rapport à l'horizon
- La lumière, la texture, les ombres
- La profondeur de champ
- Le brouillard de distance
- etc.
