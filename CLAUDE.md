# JeuFleur

Jeu co-op d'horreur en vue subjective, Godot 4.7.2 (GDScript, Forward+, Jolt), 4 joueurs max en P2P (un joueur héberge).

Toute la doc est dans `docs/modules/ROOT/` (AsciiDoc, site Antora). Lire la page du sujet **avant** de coder.

## Où chercher

| Sujet | Page |
| --- | --- |
| Le jeu en bref, liens | `pages/index.adoc` |
| Gameplay, règles du jeu | `pages/gdd/` (boucle-gameplay, objectifs, monstres, fleurs-economie, niveaux, progression…) |
| Réseau, autorité, structure du code, autoloads, Input Map, couches | `pages/architecture.adoc` |
| Pourquoi un choix technique, décisions ouvertes | `pages/decisions.adoc` |
| Ce qui est prévu, ordre des phases | `pages/roadmap.adoc` |
| Fonctionnalité existante et **ses fichiers de code** | `pages/fonctionnalites/` |
| Nommage, commits, règles Godot | `pages/guides/conventions.adoc` |
| Branches, PR, rebase, LFS | `pages/guides/git.adoc` |
| Import de modèles 3D, collisions | `pages/guides/import-modeles-3d.adoc` |
| Installer, lancer, tester le multi, générer le site | `pages/demarrage.adoc` |

Les blocs `NOTE:` marquent ce qui n'est **pas tranché** : ne pas le traiter comme une décision, demander.

## Comment travailler

1. **Question de l'utilisateur** : chercher d'abord la réponse dans la doc (table ci-dessus), répondre à partir d'elle et citer la page. Si la doc ne répond pas, le dire.
2. **Avant de coder** : vérifier que la décision est écrite dans la doc. Si elle est absente ou marquée `NOTE:`, proposer une solution et attendre la confirmation de l'utilisateur. Ne pas coder sur une décision non confirmée.
3. **Conflit** entre la doc et ce qui est demandé : le signaler (page + ce qui diffère) et demander laquelle des deux suivre, avant de coder. Ensuite, mettre la doc à jour avec la décision prise.
4. **Après une décision ou un changement de comportement** : mettre à jour la page concernée (ou la créer si l'info n'existe nulle part), dans le même commit que le code.
5. **Jamais** de commit, de push ni de PR sans l'accord explicite de l'utilisateur.

## Règles du projet

- Déplacer et renommer les fichiers uniquement depuis le dock FileSystem de Godot.
- Commiter les `.import` et `.uid` avec leur fichier.
- Ne pas modifier `project.godot` à la main (Paramètres du projet), et dans un commit `config:` séparé.
- Nouveau type de binaire : `git lfs track "*.ext"` avant de le commiter.
- Commits en français : `type: description` (`feat`, `fix`, `refactor`, `assets`, `config`, `docs`, `chore`).

## Règles de doc

- Tout changement de comportement met à jour la doc **dans le même commit**. Une nouvelle fonctionnalité a sa page dans `pages/fonctionnalites/` (modèle : `examples/modele-fonctionnalite.adoc`), avec les liens `{url-code}/chemin/fichier.gd[fichier.gd]` vers son code, et une entrée dans `nav.adoc`.
- Chaque info à un seul endroit : le **pourquoi** dans la doc, le **comment** dans le code avec des commentaires `##`. Ailleurs, un lien.
- Vérifier que le site se génère : `cd docs && npm run doc` (après un `npm install` la première fois).
