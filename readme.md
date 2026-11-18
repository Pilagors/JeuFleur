# JeuFleur

Jeu co-op d'horreur en vue subjective, fait avec Godot **4.7.2** (Forward+). Les fichiers binaires sont stockés avec **Git LFS**.

## Démarrage rapide

1. Installer [Git LFS](https://git-lfs.com/), puis une seule fois par machine :
   ```bash
   git lfs install
   ```
2. Cloner le dépôt :
   ```bash
   git clone https://github.com/Pilagors/JeuFleur.git
   ```
3. Ouvrir `project.godot` avec Godot 4.7.2 (version standard, pas .NET).

## Documentation

Toute la doc (game design, architecture, règles, guides) est dans [`docs/`](docs/modules/ROOT/pages/index.adoc), en AsciiDoc.

Pour la lire comme un site, installer [Node.js](https://nodejs.org) (version LTS), puis :

```bash
cd docs
npm install
npm run doc
```

Ouvrir ensuite `docs/build/site/jeufleur/index.html` dans un navigateur. `npm install` ne sert que la première fois.
