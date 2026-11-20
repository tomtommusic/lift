# Lift pour iPhone

Ce dossier contient le projet Xcode de l'app iOS. C'est la même app que la version web, placée dans une vraie app iPhone : icône, plein écran, hors ligne, données gardées sur l'iPhone.

Le projet ne contient pas de copie de l'app : à chaque compilation, Xcode prend `index.html`, `manifest.webmanifest` et `icons/` à la racine du dépôt. Une mise à jour de la version web est donc incluse au prochain envoi.

## Envoyer une version dans TestFlight (sans Mac)

Ça passe par GitHub, comme pour MusiDev et Planif.

### À faire une seule fois

1. **Identifiant de l'app** : sur [developer.apple.com](https://developer.apple.com/account/resources/identifiers/list), sous Identifiers, clique sur **+**, puis **App IDs → App**. Description : Lift. Bundle ID explicite : `ca.tomtommusic.lift`.
2. **Fiche App Store Connect** : sur [App Store Connect](https://appstoreconnect.apple.com), va dans **Apps → + → Nouvelle app**.
   - Plateforme : iOS
   - Nom : Lift. Si le nom est pris, essaie par exemple « Lift – Suivi d'entraînement ».
   - Langue principale : français (Canada)
   - Identifiant de paquet : `ca.tomtommusic.lift`
   - SKU : `lift`
3. **Secrets GitHub** : dans le dépôt **lift**, va dans **Settings → Secrets and variables → Actions → New repository secret**. Ajoute les 4 mêmes secrets que dans les dépôts musicdev et planif :
   - `APPLE_TEAM_ID`
   - `ASC_KEY_ID`
   - `ASC_ISSUER_ID`
   - `ASC_KEY_P8` : tout le contenu du fichier `AuthKey_XXXX.p8`

   GitHub ne permet pas de relire un secret déjà enregistré : reprends les valeurs là où tu les as notées, et le fichier `.p8` que tu as téléchargé.

### À chaque version

1. Dans le dépôt **lift**, ouvre l'onglet **Actions**, choisis **TestFlight** à gauche, puis **Run workflow**.
2. Laisse « Numéro de version » vide, ou écris par exemple `1.1`.
3. Quand l'envoi est vert, attends 10 à 30 minutes que la version apparaisse dans TestFlight. La première fois, ajoute-toi comme testeur interne dans App Store Connect, sous **TestFlight**.

## Bon à savoir

- Les données de l'app iPhone (profil, programmes, journal) sont séparées de celles de la version web dans Safari : il faut recréer son profil dans l'app.
- Elles sont conservées d'une mise à jour TestFlight à l'autre.
