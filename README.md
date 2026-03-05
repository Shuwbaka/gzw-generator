# GZW Tactical Ops Planner

Générateur de briefings et de missions pour **Gray Zone Warfare** (Lamang).  
Application 100 % front (HTML + CSS + JS) qui tourne directement dans le navigateur et stocke la configuration en local (localStorage).

## Fonctionnalités

- Générateur de missions / briefings RP à partir :
  - d’un type de mission générique (Recon, Assaut, etc.),
  - ou d’une task GZW liée à un donneur.
- Gestion des donneurs de mission (Handshake, Gunny, Lab Rat, Artisan, + donneurs personnalisés).
- Base de données de tasks :
  - création / édition / suppression,
  - association à un donneur et à un POI,
  - prévisualisation détaillée.
- Matrice POI / LZ :
  - POI configurables (nom, secteur, type),
  - LZ configurables (nom, secteur, type, POI lié),
  - générateur strict : insertion/exfil uniquement sur les LZ du POI choisi.
- Onglet Import / Export :
  - export et import en JSON pour :
    - Donneurs de mission,
    - Tasks,
    - POI,
    - LZ.
- Sauvegarde locale :
  - toutes les données (donneurs, tasks, POI, LZ, versions) sont stockées dans le navigateur via `localStorage`.
- Export du fichier :
  - bouton **SAVE HTML** pour télécharger une nouvelle version autonome de la page avec ta configuration.

## Utilisation locale

1. Télécharge le fichier `index.html` (ou `gzw-generator-*.html`).
2. Ouvre-le simplement dans ton navigateur (double-clic ou glisser-déposer dans la fenêtre du navigateur).
3. L’interface se charge, toutes les données sont stockées côté navigateur.

> Aucun serveur, aucune base de données : tout est local dans ton navigateur.

## Déploiement sur GitHub Pages

1. Créer un dépôt public sur GitHub.
2. Y ajouter le fichier `index.html` à la racine.
3. Dans les **Settings** du dépôt, section **Pages** :
   - Source : `main` (ou `master`), dossier `/root`.
4. GitHub fournit ensuite une URL du style  
   `https://tonpseudo.github.io/nom-du-depot/`.

Tu peux ensuite intégrer cette URL dans **Google Sites** via l’option d’embed (iframe).

## Import / Export (JSON)

- **Export** : les boutons d’export génèrent un fichier `.json` pour :
  - Donneurs,
  - Tasks,
  - POI,
  - LZ.
- **Import** :
  - coller du JSON dans la zone prévue, ou
  - sélectionner un fichier `.json`,
  - appliquer l’import pour remplacer la configuration locale.

Pratique pour :
- partager un set de tasks / POI / LZ avec ta team,
- synchroniser plusieurs navigateurs ou machines.

## Technologies

- HTML5
- CSS3
- JavaScript vanilla
- Stockage local : `localStorage`

Aucun framework, aucune dépendance externe.

## Licence

Ce projet est publié sous licence MIT.  
Voir le fichier `LICENSE` pour plus de détails.
