# Tutoriel 2

## @showdialog

Programme un lutin pour qu'il se déplace sur l'écran.

## Étape 1

Glisse le bloc ``||variables:définir mySprite||`` (onglet ``||Sprites:Sprites||``) dans la zone de programmation.

Dessine un vaisseau qui pointe vers le haut.

```blocks
scene.setBackgroundImage(tutorial_asset_exemple.background_1)
let mySprite = sprites.create(tutorial_asset_exemple.background_1, SpriteKind.Player)
```

```package
tutorial_asset_exemple=github:sbergeroncp/tutorial_asset_exemple
```