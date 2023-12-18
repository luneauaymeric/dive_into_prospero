# Concepts

Comme nous l'avons rappelé précédemment, les dictionnaires de concepts constituent le coeur de l'analyse sous Prospéro. Ainsi, nous avons du renseigner leur localisation dans la gestion du projet et une partie importante du travail conduit à enrichir les dictionnaires des être fictifs, des collections et des catégories. Il existe par ailleurs une multitude de façon d'accèder à ces dictionnaires. Ici nous verrons uniquement deux façons de travailler sur les dictionnaires :

1. la première passe par Prospéro

2. la seconde peut se faire en dehors de Prospéro

## Le module de gestion des concepts

![Concepts](images/concepts.png)

On y accède à travers l'onglet "concept". On commencera par les êtres fictifs. On a à gauche la liste des êtres fictifs, ensuite les "types" de désignation de l'être fictif (par exemple pour l'Etat-Central@ on a des ministères, des ministres), la liste des représentants de l'être fictif présents dans le corpus et enfin à droite la liste des représentants de l'être fictif absents du corpus. Le bouton "Énoncés/Êtres fictifs" permet d'accéder à l'ensemble des énoncés dans lesquels l'être fictif sélectionné est présent. De même, le bouton "Énoncés/représentants" affiche l'ensemble des énoncés dans lesquels le représentant sélectionné est présent. Les autres fonctionà retenir pour le moment, ce sont les boutons qui permettent de créer, supprimer ou modifier un être fictif, un type ou représentant. Ce sont les boutons "+", "-" et vide.

![Êtres fictifs](images/etre_fictif.png)

On retrouve les mêmes fonctions dans les fenêtres de gestion des collections et des catégories. À noter toutefois que dans le cas des catégories, il n'y a pas de types.



![Catégories](images/categories.png)

![Collections](images/collections.png)


## Travailler directement sur les fichiers des dictionnaires

Le contenu des dictionnaires est enregistré dans des fichiers que l'on peut ouvrir et modifier directement avec un éditeur de texte. Cela permet d'ajouter ou de supprimer en "masse" des concepts.

![Fichiers de concepts](images/fichiers_concepts.png)

La première ligne précise le type de dictionnaire. Le terme "FICTION" indique un être fictif (une collection ou une catégorie). Par exemple sur l'image ci-dessous, à gauche, on peut lire "FICTION", puis "A2I@" qui est le nom du premier être fictif du dictionnaire (par ordre alphébitique). Le mot en dessous du nom de l'être fictif désigne le "type" des représentants. Ici on a utilisé les "...", car on a pas su comment nommer le type. On a ensuite la liste des représentants. Le mot "END" signifie que la liste des représentants de ce type est terminée et qu'on passe à un autre type.

```
FICTION
ÊTRE-FICTIF1@
Type 1
représentant 1.1
représentant 1.2
représentant 1.n
END
Type 2
représentant 2.1
représentant 2.2
représentant 2.n
END
ENDFICTION
FICTION
ÊTRE-FICTIF2@
etc.
```
