# GZW Tactical Ops Planner

(Version Alpha 0.18)- - 
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

## Routine de mise à jour

1. Préparer les données dans le générateur
Ajoute / modifie :
- Donneurs (onglet Task Database),
- Tasks (Task Database),
- POI,
- LZ.
Quand tout est comme tu veux, va dans l’onglet Import / Export.

2. Exporter les 4 fichiers JSON
Dans Import / Export, fais dans cet ordre :
- Donneurs
  Clique sur Exporter donneurs (JSON) → un fichier comme gzw_vendors_export-xxx.json est téléchargé.
- Tasks
  Clique sur Exporter tasks (JSON) → un fichier gzw_tasks_export-xxx.json.
- POI
  Clique sur Exporter POI (JSON) → un fichier gzw_poi_export-xxx.json.
- LZ
  Clique sur Exporter LZ (JSON) → un fichier gzw_lz_export-xxx.json.
Tu as maintenant les 4 fichiers à jour sur ton PC.

3. Mettre à jour le dossier data sur GitHub
Va sur GitHub → repo gzw-generator.
Clique sur le dossier data.
Clique sur Add file → Upload files.
Glisse/dépose les 4 nouveaux fichiers exportés (ou utilise « Choose your files »).
Laisse GitHub te proposer de remplacer les anciens fichiers (c’est normal).
En bas de la page, mets un petit message de commit (ex : Update data JSON) et clique sur Commit changes.

4. Vérifier le résultat
Attends 30–60 secondes.
Recharge ton site GitHub Pages (Ctrl+F5 pour forcer le rafraîchissement).
Vérifie :
que les donneurs / tasks / POI / LZ affichés correspondent bien à ce que tu as exporté,
si tu demandes à un pote d’ouvrir la même URL, il voit la même base.

Aucun framework, aucune dépendance externe.

## Licence

Ce projet est publié sous licence MIT.  
Voir le fichier `LICENSE` pour plus de détails.
