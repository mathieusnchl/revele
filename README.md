# REVELE — Site MVP

Site statique mobile-first pour REVELE, service d'expériences immersives à domicile pour seniors.

## Contenu

- `index.html` : site complet (HTML, CSS et JavaScript embarqués), prêt à publier.
- `images/` : dossier volontairement vide pour vos images.

## Ajouter les images

Copiez vos fichiers dans `images/` avec exactement ces noms :

- `logo-revele.png` — logo (optionnel : le site affiche un logo typographique par défaut).
- `hero-senior-vr.jpg` — image principale de la page d'accueil.
- `senior-couple-vr.jpg` — image secondaire à utiliser dans une future section ou variante de la page.

Le point d'insertion de l'image principale est commenté directement dans `index.html` : recherchez `IMAGE HERO`. Le fichier `hero-senior-vr.jpg` est référencé par `<img src="images/hero-senior-vr.jpg">`. Si l'image n'est pas encore présente, la composition colorée reste visible grâce au comportement de secours intégré.

Pour utiliser le logo-image à la place du logo texte, remplacez le lien `.brand` dans l'en-tête par :

```html
<img src="images/logo-revele.png" alt="REVELE" class="logo-image">
```

Puis ajoutez, si besoin, `.logo-image { width: 140px; height: auto; }` dans le `<style>` de `index.html`.

## Publier sur GitHub Pages

1. Créez un dépôt GitHub (par exemple `revele-site`).
2. Décompressez l'archive et placez le contenu du dossier `revele-site/` à la racine du dépôt. Le fichier `index.html` doit être à la racine publiée.
3. Ajoutez vos images dans `images/`, validez puis poussez les fichiers :

```bash
git init
git add .
git commit -m "Publier le site REVELE MVP"
git branch -M main
git remote add origin https://github.com/VOTRE-COMPTE/revele-site.git
git push -u origin main
```

4. Dans GitHub : **Settings → Pages → Build and deployment → Deploy from a branch**.
5. Sélectionnez la branche `main`, le dossier `/ (root)`, puis **Save**.
6. Après le déploiement, GitHub affiche l'URL publique du site (souvent `https://VOTRE-COMPTE.github.io/revele-site/`).

Aucune compilation, dépendance npm ou serveur n'est nécessaire. Les polices Poppins et DM Sans sont chargées depuis Google Fonts ; une connexion est donc nécessaire pour leur rendu exact.

## Formulaire

Le formulaire est fonctionnel côté interface : il affiche un message de confirmation sans envoyer d'e-mail. Pour recevoir réellement les demandes, branchez-le à un service de formulaires (Formspree, Netlify Forms, votre API, etc.) en remplaçant le gestionnaire `submit` dans le script en bas de `index.html`.

## Accessibilité et précautions

- Navigation clavier, lien d'accès rapide, libellés de champs et message de statut inclus.
- Contraste renforcé, grandes zones tactiles et mise en page responsive.
- Les animations sont désactivées avec `prefers-reduced-motion`.
- REVELE est présenté comme une activité de loisir, pas comme un acte médical ou thérapeutique.
