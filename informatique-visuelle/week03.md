---
title: "Introduction à l'Informatique Visuelle - Semaine 3"
author: [Florian Cassayre]
date: 2018-03-06
tags: [informatique-visuelle]
...

## Computer Vision

- Image processing
- 3D reconstruction
- Visual understanding

### Projection perspective

#### Propriétés

- La colinéarité est conservée
- Les angles ne sont pas conservés
- Le parallélisme n'est pas conservé

#### Représentation matricielle

Une projection peut être représentée par un matrice $P$ de taille $3 \times 4$ (réduction de dimensionalité).

#### Calibration

#### Homographie

##### Transformation euclidienne

- 3 degrés de liberté
- Les angles, surfaces et longueurs sont conservés

##### Similarité du plan

- 4 degrés de liberté
- Les angles et les proportions des longueurs sont conservés

##### Transformation affine

- 6 degrés de liberté
- Le parallélisme, les proportions des longueurs et les surfaces sont conservés

##### Transformation projective

- 8 degrés de liberté
- Seule la colinéarité est conservée

#### Homographie 2D

Une transformation du plan dans le plan. $x' = Hx$
