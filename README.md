# Plan Projet

Application web simple pour découper un projet en tâches (4 niveaux) et les planifier sur un diagramme de Gantt, inspirée de [GanttProject](https://www.ganttproject.biz/).

En ligne : https://leomazet0809-a11y.github.io/Planning-Projet/

## Utilisation

Ouvrir `index.html` dans Chrome ou Edge (ou l'adresse ci-dessus). Aucune installation nécessaire.

### Fichiers de projet : de vrais classeurs Excel (.xlsx)
Un clic sur le **logo** en haut à gauche ramène au menu (ouvrir ou créer un projet).

Chaque projet est un classeur **`.xlsx`** enregistré sur l'ordinateur, dans le dossier choisi par l'utilisateur. Rien n'est envoyé sur Internet.
- Le classeur s'ouvre **aussi dans Excel** (double-clic ou glisser-déposer) : la feuille visible présente le planning (colonnes `N° · 1 · 2 · 3 · 4 · Responsable · Heures · Durée · Dates · Avancement · Dépend de`). Une feuille masquée contient les données propres à l'application (liens, groupes réduits, réglages).
- **Modifications faites dans Excel** (libellés, heures, lignes ajoutées…) : elles sont reprises à la prochaine ouverture dans l'application ; la mise en forme ajoutée dans Excel n'est pas conservée. Fermer le classeur dans Excel avant de l'ouvrir dans l'application (Windows empêche d'écrire dans un fichier ouvert dans Excel).
- **Nouveau projet** : choisir tout de suite le dossier et le nom du fichier. **Ouvrir un fichier** : choisir un projet `.xlsx` (un ancien fichier `.proj` est converti une fois pour toutes en `.xlsx` à l'ouverture). Un classeur Excel quelconque peut être importé dans un nouveau projet.
- **Enregistrement en temps réel** dans le fichier (Chrome / Edge). **Ctrl + S** force l'enregistrement, **Ctrl + Maj + S** (Enregistrer sous) en fait une copie ailleurs.
- Le titre du projet et le nom du fichier sont liés ; le nom du fichier ouvert est affiché dans le bandeau.
- Actualiser la page (F5) garde le projet ouvert.
- Sur les autres navigateurs (Firefox, Safari), l'enregistrement se fait en téléchargeant le fichier (Ctrl + S).

### Tableau
Des flèches grises relient chaque tâche à sa tâche mère pour visualiser la hiérarchie. Le petit chevron devant une tâche mère réduit ou déploie son groupe ; les boutons « Tout développer » (⇊) / « Tout réduire » (⇈) agissent sur le groupe sélectionné et ses sous-groupes, ou sur tout le projet si rien n'est sélectionné.

| Action | Comment |
|---|---|
| Saisir | Cliquer sur une cellule et taper au clavier (double-clic ou Entrée pour modifier le contenu existant) |
| Valider / annuler | Entrée / Échap |
| Filtrer | Bouton entonnoir : une recherche par colonne (Tâche, Responsable, Heures, Durée, Dates, Avancement), sans tenir compte des majuscules ni des accents ; les filtres se combinent. Les tâches mères des tâches trouvées restent affichées en pâle. Échap efface le filtre en cours. |
| Choisir une date | Double-clic sur Date début ou Date fin : un calendrier s'ouvre (la saisie au clavier reste possible) |
| Se déplacer | Flèches du clavier |
| Changer de niveau | Tab (niveau inférieur) · Maj + Tab (niveau supérieur), depuis une cellule des colonnes de niveau (1 à 4) |
| Déplacer une tâche | Glisser la poignée ⋮⋮ au début de la ligne (la tâche part avec ses sous-tâches) |
| Hauteur des lignes | Boutons − / + « Hauteur » ou Ctrl + molette au-dessus du tableau |
| Défiler | Molette au-dessus du tableau ou du planning (les deux restent alignés) |
| Sélectionner plusieurs cellules | Glisser la souris, ou Maj + clic, ou Maj + flèches |
| Copier / couper / coller avec Excel | Ctrl + C · Ctrl + X · Ctrl + V |
| Effacer le contenu des cellules | Retour arrière (⌫), ou Suppr dans les colonnes Responsable à Avancement |
| Supprimer les tâches sélectionnées | Suppr dans une colonne de niveau (1 à 4), puis Entrée pour confirmer (Oui) |
| Annuler / rétablir | Ctrl + Z (autant de fois que nécessaire depuis l'ouverture du projet, même après F5) / Ctrl + Y |
| Largeur d'une colonne | Glisser le bord droit de son en-tête (double-clic : taille d'origine) |

- **Durée jours** = Heures effectives × 1,5, arrondie à l'entier le plus proche (jours ouvrés, lundi → vendredi).
- Une valeur non numérique dans Heures ou Durée s'affiche en rouge et bloque le calcul.
- **Avancement** : affiché en pourcentage. Un nombre saisi (ex. `50`) affiche « 50 % » ; commencer par `=` pour un calcul (ex. `=32/3` affiche « 10,67 % » ; opérations + - * / et parenthèses). Un texte reste affiché tel quel. Une formule incorrecte s'affiche en rouge. Sur le planning, la partie réalisée de la barre est de la couleur de la tâche et le reste plus clair (barre pleine si l'avancement est vide).
- **Boutons** : au survol, une infobulle donne le nom du bouton, son rôle et son raccourci clavier.
- Modifier Durée, Date début ou Date fin recalcule les heures (arrondies à l'heure entière).
- **Tâches mères** (une tâche suivie de tâches de niveau inférieur) : Heures = somme des heures des tâches filles, Durée = somme de leurs durées, Début = début le plus tôt des filles, Date fin = fin la plus tardive des filles. Ces valeurs (en gris) ne se saisissent pas ; sur le planning, la tâche mère est une barre récapitulative noire qui couvre la période réelle de ses filles. La déplacer déplace toutes ses tâches filles.

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

### Export / import Excel et CSV
Boutons **Exporter** et **Importer** dans le bandeau (l'import existe aussi sur la page Menu, pour créer un nouveau projet).
- Format : une ligne par tâche, colonnes `N° · 1 · 2 · 3 · 4 · Responsable · Heures effectives · Durée jours · Date début · Date fin · Avancement · Dépend de`.
- Le nom de la tâche est dans la colonne de son niveau ; « Dépend de » liste les N° des tâches d'origine (ex. `2, 5`).
- Excel (`.xlsx`) : en-tête en gras et figée, vraies dates, formules d'avancement calculées par Excel. CSV : séparateur `;`, UTF-8, s'ouvre directement dans Excel en français.
- Les valeurs des tâches mères sont exportées pour information et recalculées à l'import.
- À l'import, l'application demande s'il faut créer un nouveau projet ou remplacer le projet ouvert (Ctrl + Z pour revenir en arrière). Les colonnes sont reconnues par leur titre ; un compte rendu signale les lignes ignorées.

**Fermeture** : si un projet est ouvert, le navigateur demande confirmation avant de fermer l'onglet ou la fenêtre.

**Plein écran** : bouton à quatre coins dans le bandeau, ou touche **F** (bascule) ; Échap pour en sortir. Pour taper un mot commençant par « f » dans une cellule, ouvrir d'abord la saisie (double-clic, Entrée ou F2).

**Paramètres** (roue dentée en haut à droite) : police d'écriture, couleur de fond (pour le mode clair et le mode sombre séparément) et couleur des tâches et couleur des tâches mères.

L'application peut être ajoutée aux favoris ou installée comme raccourci (menu du navigateur › « Installer Plan Projet » / « Créer un raccourci ») : elle utilise son propre logo.
