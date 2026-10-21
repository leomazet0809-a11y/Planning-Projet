# Plan Projet

Application web simple pour découper un projet en tâches (4 niveaux) et les planifier sur un diagramme de Gantt, inspirée de [GanttProject](https://www.ganttproject.biz/).

En ligne : https://leomazet0809-a11y.github.io/Planning-Projet/

## Utilisation

Ouvrir `index.html` dans Chrome ou Edge (ou l'adresse ci-dessus). Aucune installation nécessaire.

### Fichiers de projet (.proj)
Chaque projet est un fichier **`.proj`** enregistré sur l'ordinateur, dans le dossier choisi par l'utilisateur. Rien n'est envoyé sur Internet.
- **Nouveau projet** : choisir tout de suite le dossier et le nom du fichier.
- **Ouvrir un fichier** : choisir un fichier `.proj` existant. Les **fichiers récents** se rouvrent en un clic depuis la page Menu.
- **Enregistrement en temps réel** : chaque modification est écrite dans le fichier (Chrome / Edge). **Ctrl + S** force l'enregistrement, **Ctrl + Maj + S** (Enregistrer sous) en fait une copie ailleurs.
- Le nom du fichier ouvert est affiché dans le bandeau. Le navigateur ne communique pas le dossier où il se trouve.
- Sur les autres navigateurs (Firefox, Safari), l'enregistrement se fait en téléchargeant le fichier (Ctrl + S).
- Application installée (menu du navigateur › Installer) : un fichier `.proj` peut s'ouvrir par double-clic.

### Tableau
Des flèches grises relient chaque tâche à sa tâche mère pour visualiser la hiérarchie. Le petit chevron devant une tâche mère réduit ou déploie son groupe ; les boutons « Tout développer » / « Tout réduire » (doubles chevrons) agissent sur le groupe sélectionné et ses sous-groupes, ou sur tout le projet si rien n'est sélectionné.

| Action | Comment |
|---|---|
| Saisir | Cliquer sur une cellule et taper au clavier (double-clic ou Entrée pour modifier le contenu existant) |
| Valider / annuler | Entrée / Échap |
| Se déplacer | Flèches du clavier |
| Changer de niveau | Tab (niveau inférieur) · Maj + Tab (niveau supérieur), depuis une cellule des colonnes Niv |
| Déplacer une tâche | Glisser la poignée ⋮⋮ au début de la ligne (la tâche part avec ses sous-tâches) |
| Hauteur des lignes | Boutons − / + « Hauteur » ou Ctrl + molette au-dessus du tableau |
| Défiler | Molette au-dessus du tableau ou du planning (les deux restent alignés) |
| Sélectionner plusieurs cellules | Glisser la souris, ou Maj + clic, ou Maj + flèches |
| Copier / couper / coller avec Excel | Ctrl + C · Ctrl + X · Ctrl + V |
| Effacer le contenu des cellules | Retour arrière (⌫) |
| Supprimer les tâches sélectionnées | Suppr, puis Entrée pour confirmer (Oui) |
| Annuler / rétablir | Ctrl + Z (autant de fois que nécessaire depuis l'ouverture) / Ctrl + Y |
| Largeur d'une colonne | Glisser le bord droit de son en-tête (double-clic : taille d'origine) |

- **Durée jours** = Heures effectives × 1,5, arrondie à l'entier le plus proche (jours ouvrés, lundi → vendredi).
- Une valeur non numérique dans Heures ou Durée s'affiche en rouge et bloque le calcul.
- **Avancement** : texte libre (ex. « 50 % ») ; commencer par `=` pour un calcul (ex. `=32/3` affiche 10,67 ; opérations + - * / et parenthèses). Une formule incorrecte s'affiche en rouge.
- Modifier Durée, Date début ou Date fin recalcule les heures (arrondies à l'heure entière).
- **Tâches mères** (une tâche suivie de tâches de niveau inférieur) : Heures = somme des heures des tâches filles, Durée = somme de leurs durées, Début = début le plus tôt des filles, Date fin = fin la plus tardive des filles. Ces valeurs (en italique gris) ne se saisissent pas ; sur le planning, la tâche mère est une barre récapitulative noire qui couvre la période réelle de ses filles. La déplacer déplace toutes ses tâches filles.

### Planning
| Action | Comment |
|---|---|
| Déplacer une tâche | Glisser la barre à gauche ou à droite |
| Allonger / réduire | Glisser le bord droit de la barre |
| Lier deux tâches | Glisser la barre (ou le petit rond à sa droite) sur une autre tâche puis relâcher |
| Supprimer un lien | Cliquer sur la flèche |
| Zoomer / dézoomer | Boutons − / + ou Ctrl + molette |
| Revenir à aujourd'hui | Bouton « Aujourd'hui » |
| Se déplacer dans le planning | Clic gauche maintenu sur le fond et glisser dans tous les sens |

Une tâche liée commence toujours après la fin de sa tâche d'origine et suit ses déplacements.
Les samedis et dimanches sont grisés : aucune tâche ne peut y commencer ou y finir.

**Paramètres** (roue dentée en haut à droite) : police d'écriture, couleur de fond (pour le mode clair et le mode sombre séparément) et couleur des tâches et couleur des tâches mères.

L'application peut être ajoutée aux favoris ou installée comme raccourci (menu du navigateur › « Installer Plan Projet » / « Créer un raccourci ») : elle utilise son propre logo.
