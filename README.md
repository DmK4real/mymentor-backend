# MyMentor Front Pages

Ce dépôt contient la page d'accueil (landing page) et les supports HTML statiques associés au programme MyMentor.

## Structure principale
- `index.html` : page d'accueil refondue avec sections sémantiques et feuilles de style externes.
- `assets/css/main.css` : feuille de style partagée (typographies, couleurs, grilles responsives, animations).
- Autres fichiers `*_flyer.html`, `landing.html`, etc. : pages historiques avec styles en ligne.

## Intégrer la nouvelle page d'accueil
1. **Copier les fichiers nécessaires** dans votre hébergement (GitHub Pages, Netlify, serveur FTP, etc.) :
   - le fichier `index.html` à la racine du site ;
   - le dossier `assets/css/` contenant `main.css`.
2. **Vérifier les chemins** : l'attribut `href="assets/css/main.css"` dans la balise `<link>` d'`index.html` suppose que le dossier `assets/` est voisin du fichier HTML. Si vous placez la page dans un autre répertoire, adaptez ce chemin (ex. `../assets/css/main.css`).
3. **Relier les autres pages** (facultatif mais recommandé) : pour appliquer la même identité visuelle à vos autres pages HTML, ajoutez l'import de la feuille de style dans l'élément `<head>` :
   ```html
   <link rel="stylesheet" href="/assets/css/main.css">
   ```
   Supprimez ensuite les blocs `<style>` internes pour éviter les conflits.
4. **Tester en local** : servez le dossier avec n'importe quel serveur statique (ex. `python -m http.server 8000`) puis ouvrez `http://localhost:8000/index.html` dans votre navigateur pour vérifier le rendu et les liens.

## Personnaliser le design
- Les couleurs principales et secondaires se trouvent au début de `assets/css/main.css` dans les variables CSS (`--color-*`).
- Les espacements et tailles de police sont définis via les variables `--space-*` et `--font-*`.
- Les composants réutilisables (cartes, boutons, grilles) disposent de classes préfixées `card__`, `auth-btn`, `grid--*` que vous pouvez décliner au besoin.

## Accessibilité et SEO
- Conservez les attributs `aria-*`, les balises structurantes (`<header>`, `<main>`, `<section>`, `<nav>`) et les balises meta pour garder un bon niveau d'accessibilité.
- Mettez à jour le contenu textuel (titres, descriptions, CTA) pour refléter votre proposition de valeur tout en respectant la structure existante.

## Prévisualisation rapide
```bash
python -m http.server 8000
# Ouvrir ensuite http://localhost:8000/index.html
```

Ces étapes suffisent pour intégrer la page d'accueil améliorée dans n'importe quel hébergement statique.
