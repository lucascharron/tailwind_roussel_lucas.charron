# Site de Fleurs Roussel

Bonjour Madame Roussel,

Ce document explique comment est fait le site de votre boutique et comment y modifier les textes, les prix et les images.

## Ce que contient le site

Le site est une seule page, `index.html`, qui se lit de haut en bas :

1. **L'en-tête** : le logo, le nom de la boutique, le menu (Bouquets, Ateliers, Livraison, Contact) et le bouton « Commander ».
2. **L'introduction** : « Des fleurs de saison, composées à la main », avec deux boutons et la photo d'un bouquet.
3. **Les bouquets de la semaine** : trois cartes (Bouquet du marché, Roses anciennes, Champêtre), chacune avec son prix.
4. **Pourquoi choisir Fleurs Roussel ?** : vos trois atouts (fleurs de saison, livraison le jour même, composées à la main).
5. **L'atelier** : le samedi par mois où vous apprenez à composer un bouquet.
6. **Le pied de page** : l'adresse, les horaires, le téléphone et les liens utiles.

Quand on clique sur un lien du menu, la page défile jusqu'à la bonne section.

## Où se trouve quoi

| Dossier ou fichier | Rôle |
|---|---|
| `index.html` | Tous les textes et la structure de la page |
| `img_roussel/` | Le logo, les illustrations des bouquets et de l'atelier, les icônes |
| `src/input.css` | Les couleurs et les polices du site |
| `dist/output.css` | La feuille de style fabriquée automatiquement. Ne la modifiez pas à la main. |

## Comment modifier le site

- **Changer un texte, un prix ou un horaire** : ouvrez `index.html` dans un éditeur de texte, cherchez le texte (par exemple « 35 € ») et remplacez-le. Ne touchez pas aux mots entre `<` et `>`.
- **Changer une image** : remplacez le fichier dans `img_roussel/` en gardant exactement le même nom.
- **Changer une couleur** : elles sont toutes au même endroit, en haut de `src/input.css` (`framboise`, `bordeaux`, `sauge`, `creme`, `petale`, `encre`, `blanc`). Modifiez le code couleur, par exemple `#B83B5E`, et toutes les pages suivront.

Le site est fabriqué avec **Tailwind CSS**. Les mots comme `bg-framboise` ou `text-xs` dans `index.html` sont des consignes de mise en forme. Il n'est pas nécessaire de les comprendre pour changer un texte.

## Installer et fabriquer le site

Après avoir modifié le site, il faut régénérer la feuille de style. Ouvrez un terminal dans le dossier du projet.

```
npm init -y
npm install tailwindcss @tailwindcss/cli
npx @tailwindcss/cli -i ./src/input.css -o ./dist/output.css --watch
```

La dernière commande reste active et se met à jour toute seule à chaque modification. Arrêtez-la avec `Ctrl + C`.

Si vous récupérez le projet sur un autre ordinateur, lancez d'abord :

```
npm install
```

Pour fabriquer la version finale, plus légère, lancez :

```
npm run build
```

Ouvrez ensuite `index.html` dans votre navigateur pour voir le site.

## Bon à savoir

- Le dossier `node_modules` est créé par `npm install`. Il est volumineux et ne doit pas être envoyé avec le projet : il se recrée avec la commande.
- Les boutons « Commander » et les liens ne mènent pas encore vers une vraie commande : c'est une première version de l'affichage.
- Les polices (Inter et Playfair Display) viennent de Google Fonts et nécessitent une connexion internet.
