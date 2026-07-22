# Bouk's Budget — déploiement sur GitHub Pages

Ce dossier contient tout ce qu'il faut pour héberger l'application gratuitement
sur GitHub et l'installer comme une vraie app sur votre téléphone.

## Fichiers du dossier
- `index.html` — l'application
- `manifest.json` — décrit l'app pour qu'elle soit "installable"
- `sw.js` — permet le fonctionnement hors-ligne
- `icon-192.png`, `icon-512.png`, `icon-180.png` — l'icône de l'app
- `shortcut-expense.png`, `shortcut-income.png` — icônes des raccourcis (appui long sur l'icône de l'app)

⚠️ Ces 8 fichiers doivent rester **à la racine** du dépôt (pas dans un sous-dossier),
sauf si vous adaptez les chemins dans `index.html` et `manifest.json`.

## Étapes

1. **Créer un dépôt GitHub**
   - Allez sur [github.com/new](https://github.com/new)
   - Donnez-lui un nom, par exemple `budget24`
   - Laissez-le public, cochez "Add a README" si vous voulez, puis créez-le

2. **Ajouter les fichiers**
   - Dans le dépôt, cliquez sur **Add file → Upload files**
   - Glissez-déposez les 6 fichiers de ce dossier (`index.html`, `manifest.json`, `sw.js`, les 3 `.png`)
   - Cliquez sur **Commit changes**

3. **Activer GitHub Pages**
   - Dans le dépôt, allez dans **Settings → Pages**
   - Sous "Build and deployment", choisissez **Branch: main**, dossier **/ (root)**
   - Cliquez sur **Save**
   - Au bout d'une à deux minutes, l'URL apparaît en haut, du type :
     `https://votre-nom-utilisateur.github.io/budget24/`

4. **Installer sur votre téléphone**
   - Ouvrez cette URL dans **Chrome** (Android) ou **Safari** (iPhone)
   - Chrome : menu **⋮ → Installer l'application** (ou "Ajouter à l'écran d'accueil")
   - Safari : bouton **Partager → Sur l'écran d'accueil**
   - L'icône Bouk's Budget apparaît sur votre écran d'accueil, l'app s'ouvre en plein écran

## Vos données
Les transactions et réglages sont stockés directement dans le navigateur de
votre téléphone (rien n'est envoyé sur un serveur). Si vous changez de
téléphone ou videz les données du navigateur, l'historique sera perdu — il n'y
a pas de sauvegarde automatique en ligne avec cette version.

## (Optionnel) Ajouter des captures d'écran à la fenêtre d'installation
Chrome peut afficher un aperçu de l'app dans sa fenêtre d'installation si le
`manifest.json` contient un bloc `screenshots`. Comme ces images doivent être
de vraies captures de l'app (je ne peux pas les générer moi-même), voici comment
faire :

1. Ouvrez l'app dans Chrome sur votre téléphone, prenez 1 à 3 captures d'écran
   (écran principal, liste des dépenses, etc.)
2. Ajoutez-les au dépôt, par exemple `screenshot-1.png`
3. Ajoutez ce bloc dans `manifest.json`, juste avant le `}` final, après `"shortcuts"` :
   ```json
   ,"screenshots": [
     { "src": "screenshot-1.png", "sizes": "1080x2340", "type": "image/png", "form_factor": "narrow" }
   ]
   ```
   (adaptez `sizes` à la résolution réelle de votre capture)
