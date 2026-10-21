# Plan Projet

Application web simple pour découper un projet en tâches (4 niveaux) et les planifier sur un diagramme de Gantt, inspirée de [GanttProject](https://www.ganttproject.biz/).

En ligne : https://leomazet0809-a11y.github.io/Planning-Projet/

## Utilisation

Ouvrir `index.html` dans Chrome ou Edge (ou l'adresse ci-dessus). Aucune installation nécessaire.
Les données sont enregistrées dans le navigateur ; **Exporter** (page Menu) crée un fichier de sauvegarde, **Importer** le recharge.

### Tableau
| Action | Comment |
|---|---|
| Saisir | Cliquer sur une cellule et taper au clavier (double-clic ou Entrée pour modifier le contenu existant) |
| Valider / annuler | Entrée / Échap |
| Se déplacer | Flèches du clavier |
| Changer de niveau | Tab (niveau inférieur) · Maj + Tab (niveau supérieur) |
| Sélectionner plusieurs cellules | Glisser la souris, ou Maj + clic, ou Maj + flèches |
| Copier / couper / coller avec Excel | Ctrl + C · Ctrl + X · Ctrl + V |
| Effacer | Suppr |
| Largeur d'une colonne | Glisser le bord droit de son en-tête (double-clic : taille d'origine) |

- **Durée jours** = Heures effectives × 1,5, arrondie à l'entier le plus proche (jours ouvrés, lundi → vendredi).
- Une valeur non numérique dans Heures ou Durée s'affiche en rouge et bloque le calcul.
- Modifier Durée, Date début ou Date fin recalcule les heures (arrondies à l'heure entière).

### Planning
| Action | Comment |
|---|---|
| Déplacer une tâche | Glisser la barre à gauche ou à droite |
| Allonger / réduire | Glisser le bord droit de la barre |
| Lier deux tâches | Glisser la barre (ou le petit rond à sa droite) sur une autre tâche puis relâcher |
| Supprimer un lien | Cliquer sur la flèche |
| Zoomer / dézoomer | Boutons − / + ou Ctrl + molette |
| Revenir à aujourd'hui | Bouton « Aujourd'hui » |

Une tâche liée commence toujours après la fin de sa tâche d'origine et suit ses déplacements.
Les samedis et dimanches sont grisés : aucune tâche ne peut y commencer ou y finir.

**Enregistrer** (ou Ctrl + S) confirme l'enregistrement du projet.
