# Pour importer des modèles 3D

1. Glisser / déposer dans le dossier `/assets/models` le fichier `.glb / .gltf` du modèle
2. Sélectionner le fichier scène ainsi importé
3. Sur le panel de gauche, cliquer sur le menu `Importer`
4. Cliquer sur `Avancés`

## Dans la fenêtre de paramêtres d'imports

Se renseigner sur ce tableau pour définir le noeud racine associé et le type de forme.

| Personnage      | Object (sans physique) | Object (avec physique) | Structure    |
|-----------------|------------------------|------------------------|--------------|
| CharacterBody3D | RigidBody3D            | StaticBody3D           | StaticBody3D |


| Trimesh                                                                 | Single Convex    | Decompose Convex |
|-------------------------------------------------------------------------|------------------|----------------- |
| Pour que les détails de l'objets soit pris en compte plus distinctement | Forme simplifiée | Entre-deux       |

### Personnage

Pour définir le noeud racine, sélectionner la scène parente et, dans le panel de droite, sélectionner le `Type de Racine` associé.

Si une animation type ***Idle*** ou de ***Mouvement*** est disponible, cliquer dessus et définir la boucle en ***Linear***.

> [!WARNING]
> Pour chacune des modifications qui vous semble important dans la section des paramêtres d'import, renseignez son utilité dans la doc pour les autres fois.

### Structure / Objets

Pour un import avec des collisions built-in :

1. Sélectionner le `MeshInstance3D` qui devrait recevoir une collision
2. Sous le menu `Générer`, activer `Physique`
3. Sous le menu `Physique`
    - Sélectionner le `Type de corps` associé au type dans le tableau ci-dessus
    - Sélectionner le `Type de forme` associé au type dans le tableau ci-dessus

## Quand tout a été modifié

Cliquer `Réimporter`

# Pour utiliser correctement dans les scènes

### Sauvegarder la scène

1. Clic droit sur le model
2. Sélectionner `Nouvelle scène héritée`
3. Vérifier que le noeud parent est bien celui défini dans l'import
4. Sauvegarder la scène dans `/scenes/<nom_objet>`

### Utilisation dans une autre scène

1. Sélectionner la scène où importer l'objet
2. Clic droit sur la scène de l'objet précédemment sauvegardée
3. Sélectionner `Instancier`

> [!NOTE]
> Si il manque des informations, ou que ce n'est pas clair, allez vous faire enculer