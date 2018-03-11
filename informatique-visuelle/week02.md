---
title: "Introduction à l'Informatique Visuelle - Semaine 2"
author: [Florian Cassayre]
date: 2018-02-27
tags: [informatique-visuelle]
...

## Géométrie 3D

### Représentation

La représentation d'une surface 3D peut se faire avec un maillage de triangles. Plus la taille des triangle est petite plus lisse sera la surface.


### Transformations

Une transformation linéaire satisfait les propriétés suivantes :

  1. $T(a + b) = T(a) + T(b)$
  2. $T(\alpha a) = \alpha T(a)$

Pour effectuer une transformation en **coordonnées homogènes** dans un espace à $n$ dimensions il faut une matrice de transformation $(n + 1) \times (n + 1)$.

$$
\begin{bmatrix}
    x \\ y \\ z \\ 1
\end{bmatrix}
\sim
\begin{bmatrix}
    sx \\ sy \\ sz \\ s
\end{bmatrix}
$$

#### Scaling

$$
\begin{bmatrix}
    v_x' \\ v_y' \\ v_z' \\ v_w'
\end{bmatrix}
=
\begin{bmatrix}
    s_x & 0 & 0 & 0 \\
    0 & s_y & 0 & 0 \\
    0 & 0 & s_z & 0 \\
    0 & 0 & 0 & 1
\end{bmatrix}
\begin{bmatrix}
    v_x \\ v_y \\ v_z \\ v_w
\end{bmatrix}
$$

#### Rotation

##### Axe $x$

$$
\begin{bmatrix}
    v_x' \\ v_y' \\ v_z' \\ v_w'
\end{bmatrix}
=
\begin{bmatrix}
    1 & 0 & 0 & 0 \\
    0 & cos(\theta) & -sin(\theta) & 0 \\
    0 & sin(\theta) & cos(\theta) & 0 \\
    0 & 0 & 0 & 1 \\
\end{bmatrix}
\begin{bmatrix}
    v_x \\ v_y \\ v_z \\ v_w
\end{bmatrix}
$$

##### Axe $y$

$$
\begin{bmatrix}
    v_x' \\ v_y' \\ v_z' \\ v_w'
\end{bmatrix}
=
\begin{bmatrix}
    cos(\theta) & 0 & -sin(\theta) & 0 \\
    0 & 1 & 0 & 0 \\
    sin(\theta) & 0 & cos(\theta) & 0 \\
    0 & 0 & 0 & 1 \\
\end{bmatrix}
\begin{bmatrix}
    v_x \\ v_y \\ v_z \\ v_w
\end{bmatrix}
$$


##### Axe $z$

$$
\begin{bmatrix}
    v_x' \\ v_y' \\ v_z' \\ v_w'
\end{bmatrix}
=
\begin{bmatrix}
    cos(\theta) & -sin(\theta) & 0 & 0 \\
    sin(\theta) & cos(\theta) & 0 & 0 \\
    0 & 0 & 1 & 0 \\
    0 & 0 & 0 & 1
\end{bmatrix}
\begin{bmatrix}
    v_x \\ v_y \\ v_z \\ v_w
\end{bmatrix}
$$

#### Shear

$$
\begin{bmatrix}
    v_x' \\ v_y' \\ v_z' \\ v_w'
\end{bmatrix}
=
\begin{bmatrix}
    1 & a_y & a_z & 0 \\
    a_x & 1 & b_z & 0 \\
    b_x & b_y & 1 & 0 \\
    0 & 0 & 0 & 1 \\
\end{bmatrix}
\begin{bmatrix}
    v_x \\ v_y \\ v_z \\ v_w
\end{bmatrix}
$$

#### Translation

$$
\begin{bmatrix}
    v_x' \\ v_y' \\ v_z' \\ v_w'
\end{bmatrix}
=
\begin{bmatrix}
    1 & 0 & 0 & t_x \\
    0 & 1 & 0 & t_y \\
    0 & 0 & 1 & t_z \\
    0 & 0 & 0 & 1
\end{bmatrix}
\begin{bmatrix}
    v_x \\ v_y \\ v_z \\ v_w
\end{bmatrix}
$$

#### Concaténation

Les opérations peuvent être concaténées. Attention, l'ordre des opérations importe !


#### Gimbal lock

Problème avec le système des angles d'Euler où un degré de liberté est "perdu".

#### Quaternions

Une autre représentation des angles, plus compliquée, mais qui à l'avatage de contourner le problème du _gimbal lock_.


## Rendu

### Projection

C'est le processus de conversion d'une scène 3D en une image (2D).

On distingue deux types de projection :

- Projection orthographique
- Projection perspective



### Ombres
