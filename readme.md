# Guide pour récupérer le projet

Projet Godot **4.7.2** (Forward+). Les fichiers binaires (images, modèles 3D, audio, polices) sont stockés avec **Git LFS**.

## Installation

1. Installer [Git LFS](https://git-lfs.com/).
2. Activer LFS (une seule fois par machine) :
   ```bash
   git lfs install
   ```
3. Cloner le dépôt :
   ```bash
   git clone https://github.com/Pilagors/JeuFleur.git
   ```

> Si une asset ne s'importe pas, c'est que LFS n'était pas actif au moment du clone. <br> `git lfs pull` pour récupérer les fichiers.

## Organisation

| Dossier | Contenu |
|---|---|
| `scenes/` | Scènes Godot (`.tscn`) |
| `scripts/` | Scripts GDScript (`.gd`) |
| `assets/images/` | Textures et images |
| `assets/models/` | Modèles 3D (de préférence `.glb`) |
| `assets/shaders/` | Shaders (`.gdshader`) |
| `assets/audio/` | Sons et musiques (`.mp3`, `.ogg`, `.wav`) |

## Règles à respecter

- **Déplacer et renommer les fichiers uniquement depuis le dock FileSystem de Godot**, jamais depuis l'explorateur. Sinon les références entre fichiers cassent.
- **Commiter les fichiers `.import` et `.uid`** avec leur fichier associé : ils contiennent les réglages d'import et les identifiants utilisés par les scènes.
- **Ne jamais commiter `.godot/`** (c'est un cache local, déjà ignoré).
- **Modifier la config via `Projet → Paramètres du projet`**, pas à la main dans `project.godot`. Mettre ces changements dans un commit séparé.
- Pour un nouveau type de fichier binaire, l'ajouter à LFS (`git lfs track "*.ext"`) **avant** de le commiter.

### Messages de commit

Format `type: description`, par exemple :

- `feat:` nouvelle fonctionnalité (`feat: arrosage des fleurs`)
- `fix:` correction de bug
- `assets:` ajout ou modification d'assets
- `config:` changement dans les paramètres du projet
- `refactor:` réorganisation sans changement de comportement
