# Plan Projet

Application web simple pour découper un projet en tâches (jusqu'à 10 niveaux) et les planifier sur un diagramme de Gantt, inspirée de [GanttProject](https://www.ganttproject.biz/).

En ligne : https://leomazet0809-a11y.github.io/Planning-Projet/

## Utilisation

Ouvrir `index.html` dans Chrome ou Edge (ou l'adresse ci-dessus). Aucune installation nécessaire.

### Fichiers de projet : de vrais classeurs Excel (.xlsx)
Un clic sur le **logo** en haut à gauche ramène au menu (ouvrir ou créer un projet).

Chaque projet est un classeur **`.xlsx`** enregistré sur l'ordinateur, dans le dossier choisi par l'utilisateur. Rien n'est envoyé sur Internet.
- Le classeur s'ouvre **aussi dans Excel** (double-clic ou glisser-déposer) : la feuille visible présente le planning (colonnes `N° · 1 · 2 · 3 · 4 · Responsable · Heures · Durée · Dates · Avancement · Dépend de · Commentaires`). Une feuille masquée contient les données propres à l'application (liens, groupes réduits, réglages).
- **Modifications faites dans Excel** (libellés, heures, lignes ajoutées…) : elles sont reprises à la prochaine ouverture dans l'application ; la mise en forme ajoutée dans Excel n'est pas conservée. Fermer le classeur dans Excel avant de l'ouvrir dans l'application (Windows empêche d'écrire dans un fichier ouvert dans Excel).
- **Nouveau projet** : choisir tout de suite le dossier et le nom du fichier. **Ouvrir un fichier** : choisir un projet `.xlsx` (un ancien fichier `.proj` est converti une fois pour toutes en `.xlsx` à l'ouverture). Un classeur Excel quelconque peut être importé dans un nouveau projet.
- **Enregistrement en temps réel** dans le fichier (Chrome / Edge). **Ctrl + S** force l'enregistrement, **Ctrl + Maj + S** (Enregistrer sous) en fait une copie ailleurs.
- Le titre du projet est le nom du fichier ; il n'est pas modifiable dans l'application (pour renommer : « Enregistrer sous », ou renommer le fichier dans l'Explorateur). À droite du titre s'affiche le fichier ouvert : son chemin à partir du **dossier de travail** (ex. « Projets › Chantier A › Planning.xlsx »), ou son nom seul s'il est rangé ailleurs. Le dossier de travail se choisit une fois sur la page d'accueil ou dans Paramètres (le navigateur ne permet pas d'afficher le chemin complet C:\…) ; les fenêtres Ouvrir / Enregistrer s'ouvrent directement dans ce dossier.
- Bouton **Annuler** (flèche retour, en haut) : revient en arrière d'une action, comme Ctrl + Z.
- Actualiser la page (F5) garde le projet ouvert.
- Sur les autres navigateurs (Firefox, Safari), l'enregistrement se fait en téléchargeant le fichier (Ctrl + S).

### Tableau
Des flèches grises relient chaque tâche à sa tâche mère pour visualiser la hiérarchie. Le petit chevron devant une tâche mère réduit ou déploie son groupe ; les boutons « Tout développer » (⇊) / « Tout réduire » (⇈) agissent sur le groupe sélectionné et ses sous-groupes, ou sur tout le projet si rien n'est sélectionné.

| Action | Comment |
|---|---|
| Saisir | Cliquer sur une cellule et taper au clavier (double-clic, Entrée ou F2 pour modifier le contenu existant) |
| Colonne Tâche | Dans l'application, le nom de la tâche occupe une seule colonne « Tâche » (retrait selon le niveau, largeur réglable) ; dans Excel et pour le copier / coller, il reste réparti sur une colonne par niveau (1, 2, 3, 4… : 4 colonnes au moins, jusqu'à 10 si le projet a des tâches aussi fines) |
| Renommer une tâche | Un simple clic sur son nom (colonne Tâche) ouvre la modification après un court instant |
| Commentaires | Double-clic sur le nom de la tâche, ou sur sa barre dans le planning : une fenêtre s'ouvre ; la croix (ou Échap) la ferme et enregistre. Une bulle signale les tâches commentées (dans le tableau, et au survol de la barre). Les commentaires sont aussi dans la colonne « Commentaires » du fichier Excel |
| Valider / annuler | Entrée / Échap |
| Filtrer | Bouton entonnoir : une recherche par colonne (Tâche, Responsable, Heures, Durée, Dates, Avancement), sans tenir compte des majuscules ni des accents ; les filtres se combinent. Les tâches mères des tâches trouvées restent affichées en pâle. Échap efface le filtre en cours. |
| Choisir une date | Double-clic sur Date début ou Date fin : un calendrier s'ouvre (la saisie au clavier reste possible) |
| Se déplacer | Flèches du clavier |
| Changer de niveau | Tab (niveau inférieur) · Maj + Tab (niveau supérieur), depuis la colonne Tâche ; le niveau se voit au retrait du nom |
| Déplacer une tâche | Glisser la poignée ⋮⋮ au début de la ligne (la tâche part avec ses sous-tâches) |
| Hauteur des lignes | Boutons − / + « Hauteur » ou Ctrl + molette au-dessus du tableau |
| Défiler | Molette au-dessus du tableau ou du planning (les deux restent alignés) |
| Sélectionner plusieurs cellules | Glisser la souris, ou Maj + clic, ou Maj + flèches |
| Copier / couper / coller avec Excel | Ctrl + C · Ctrl + X · Ctrl + V |
| Effacer le contenu des cellules | Retour arrière (⌫), ou Suppr dans les colonnes Responsable à Avancement |
| Supprimer les tâches sélectionnées | Suppr dans la colonne Tâche, puis Entrée pour confirmer (Oui) |
| Monter / descendre une tâche | Alt + ↑ / Alt + ↓ : la tâche (avec ses sous-tâches) passe au-dessus / en dessous de la tâche voisine du même groupe |
| Annuler / rétablir | Ctrl + Z (autant de fois que nécessaire depuis l'ouverture du projet, même après F5) / Ctrl + Y |
| Largeur d'une colonne | Glisser le bord droit de son en-tête (double-clic : taille d'origine) |

- **Durée jours** = Heures effectives × coefficient (1,5 par défaut), arrondie à l'entier le plus proche (jours ouvrés, lundi → vendredi). Le coefficient est propre à chaque projet : Paramètres (roue dentée) › Projet en cours. Une durée saisie directement est gardée telle quelle.
- **Calculs** : dans Heures effectives et Durée jours, une saisie commençant par `=` est un calcul (`=2*5` affiche 10 ; + - * / et parenthèses) ; le calcul reste modifiable.
- Une valeur non numérique dans Heures ou Durée s'affiche en rouge et bloque le calcul.
- **Avancement** : affiché en pourcentage. Un nombre saisi (ex. `50`) affiche « 50 % » ; commencer par `=` pour un calcul (ex. `=32/3` affiche « 10,67 % » ; opérations + - * / et parenthèses). Un texte reste affiché tel quel. Une formule incorrecte s'affiche en rouge. Sur le planning, la partie réalisée de la barre est de la couleur de la tâche et le reste plus clair (barre pleine si l'avancement est vide).
- **Boutons** : au survol, une infobulle donne le nom du bouton, son rôle et son raccourci clavier.
- Modifier Durée, Date début ou Date fin recalcule les heures (arrondies à l'heure entière).
- **Tâches mères** (une tâche suivie de tâches de niveau inférieur) : Heures = somme des heures des tâches filles, Durée = somme de leurs durées, Début = début le plus tôt des filles, Date fin = fin la plus tardive des filles. Ces valeurs (en gris) ne se saisissent pas ; sur le planning, la tâche mère est une barre récapitulative gris clair qui couvre la période réelle de ses filles. La déplacer déplace toutes ses tâches filles.

### Planning
| Action | Comment |
|---|---|
| Déplacer une tâche | Glisser la barre à gauche ou à droite |
| Allonger / réduire | Glisser le bord droit de la barre |
| Placer une tâche non planifiée | Double-clic sur le planning, sur sa ligne, au jour voulu : elle y commence (1 jour si elle n'a pas encore de durée) |
| Lier deux tâches | Glisser le petit rond à droite de la barre sur une autre tâche puis relâcher (glisser le milieu de la barre la déplace seulement) ; pendant le glissement, la ligne visée est surlignée dans le planning et dans le tableau (en rouge si le lien est impossible) |
| Supprimer un lien | Cliquer sur la flèche |
| Tâche liée décalée | Si une tâche liée commence plus tard que le plus tôt possible, sa flèche est en pointillés (le survol indique l'écart en jours ouvrés) |
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

**Plein écran** : bouton à quatre coins dans le bandeau ; Échap pour en sortir.

**Paramètres** (roue dentée en haut à droite) : police d'écriture, couleur de fond (pour le mode clair et le mode sombre séparément) et couleur des tâches et couleur des tâches mères.

L'application peut être ajoutée aux favoris ou installée comme raccourci (menu du navigateur › « Installer Plan Projet » / « Créer un raccourci ») : elle utilise son propre logo.
