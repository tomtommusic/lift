# Lift

Application web de suivi d'entraînement, pensée pour le téléphone.

- Profil (sexe, âge, poids, grandeur, % de gras) et calories de maintien (Mifflin-St Jeor, Katch-McArdle)
- Programmes enregistrés, programme actif, création sur un canevas vide ou génération automatique
- Librairie de 186 exercices illustrés et animés : musculation, mobilité, stabilisateurs, tendons
- Création d'exercices personnalisés avec photo
- Journal par exercice (poids, reps, tempo, notes), historique et courbes de progression
- Calcul des disques à mettre sur la barre

## Utiliser l'app

L'app est publiée avec GitHub Pages : https://tomtommusic.github.io/lift/

Sur iPhone, ouvre le lien dans Safari, puis Partager → « Sur l'écran d'accueil ». L'app s'ouvre alors en plein écran et fonctionne hors ligne.

## Données

Tout est gardé dans le navigateur de l'appareil (localStorage). Rien n'est envoyé sur Internet.
Pour garder une copie ou changer d'appareil : Profil → Réglages → Sauvegarde de mes données.

## Structure

- `index.html` : toute l'app (HTML, CSS et JavaScript dans un seul fichier)
- `manifest.webmanifest` et `icons/` : installation sur l'écran d'accueil
- `sw.js` : fonctionnement hors ligne. Change `VERSION` à chaque mise à jour.

## À venir

- Silhouette féminine pour les illustrations quand le profil est « Femme »
