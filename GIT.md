# Comment modifier le dernier commit

Lorsque vous travaillez sur vos branches, il arrive que vous commitez et pushez des fichiers que vous remodifiez. Il existe un moyen de faire une `Correction de commit`.

Le plus simple d'utilisation est avec la commande `git citool`.

## Interface Git Citool

L'interface s'ouvre et 4 blocs sont visible.

- **Unstaged Changes** : Les fichiers qui n'ont pas été `git add`
- **Staged Changes** : Les fichier qui ont été `git add`
- **Bloc central** : Le contenu du fichier sélectionné.
- **Panel inférieur** : Les actions avec le message du commit et la checkbox `Amend Last Commit`.

En cliquant sur les logos des fichiers, vous pouvez ajouter ou retirer des fichiers dans le commit.

Avant d'ajouter vos fichiers dans les **Staged Changes**, vous pouvez activer `Amend Last Commit` pour modifier le dernier commit en date.

Quand tout a été modifié comme vous le souhaitez, cliquer sur `commit`.

> [!CAUTION]
> Ne jamais cliquer sur push

## Si vous modifiez le dernier commit

1. Faire les modifications des fichiers
2. Ouvrir `git citool`
3. Cliquer sur `Amend Last Commit`
4. Ajouter les fichiers depuis l'interface
5. (OPTIONNEL) Modifier le message de commit en fonction de la modification
6. Cliquer sur `Commit`
7. Push avec `git push --force-with-lease`

## Si vous modifiez le N-ième dernier commit

1. Entrer `git rebase -i HEAD~N`
2. Modifier le début de la ligne de `pick` à `e`
3. Sauvegarder les changements
4. Faire les modifications des fichiers
5. Ouvrir `git citool`
6. Cliquer sur `Amend Last Commit`
7. Ajouter les fichiers depuis l'interface
8. (OPTIONNEL) Modifier le message de commit en fonction de la modification
9. Cliquer sur `Commit`
10. Entrez `git rebase --continue`
11. Push avec `git push --force-with-lease`

> [!NOTE]
> Si vous avez des problèmes avec VSCode qui modifie mal le fichier de rebase, entrez `git config --global core.editor "code --wait"`. Il suffira de modifier le fichier directement, sauvegarder et fermer le fichier

> Soit pas con, met pas N, met la distance entre le commit actuel et celui que tu veux modifier

