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

## Comment le site s'adapte à l'écran

Le site s'affiche correctement sur téléphone, tablette et ordinateur, sans jamais défiler de côté (de 360 à 1440 px de large).

| Écran | Largeur | Ce que l'on voit |
|---|---|---|
| Téléphone | jusqu'à 639 px | tout est en une seule colonne ; le menu passe sous le logo ; les boutons sont l'un sous l'autre |
| Grand téléphone | à partir de 640 px | les boutons de l'introduction sont côte à côte ; les bouquets s'affichent par deux |
| Tablette | à partir de 768 px | l'en-tête tient sur une ligne ; l'introduction, les atouts, l'atelier et le pied de page passent en colonnes ; les titres grandissent |
| Ordinateur | à partir de 1024 px | les trois bouquets sont sur la même ligne ; le titre de l'introduction est au maximum |

Sur les très grands écrans, le contenu reste centré et ne dépasse pas 1152 px de large, pour que le texte reste agréable à lire.

## Pour naviguer au clavier et à la souris

- Tous les liens et boutons changent d'apparence quand on passe la souris dessus.
- Quand on se déplace avec la touche Tab, le lien ou le bouton choisi est entouré d'un contour bien visible.
- Les images ont un texte alternatif pour les personnes qui utilisent un lecteur d'écran.

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

Quelques repères si vous les croisez : `sm:`, `md:` et `lg:` devant un mot signifient « à partir de cette taille d'écran » (voir le tableau plus haut). `hover:` s'applique au survol de la souris, et `focus-visible:` à la navigation au clavier.

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
- Les boutons « Commander » et « Réserver une place », ainsi que les liens « Livraison » et « Mentions légales », ne mènent pas encore vers une vraie page : ils servent pour l'instant à l'affichage.
- Les polices (Inter et Playfair Display) viennent de Google Fonts et nécessitent une connexion internet.
