# Tutoriel 3 C

## @showdialog

Programme un lutin et un projectile.

## Étape 1

Ajoute le bloc ``||scene:définir image d'arrière-plan||`` (onglet ``||scene:Scène||``) dans le bloc ``||loops:au démarrage||``.

Choisis un arrière-plan.

```blocks

scene.setBackgroundImage(tutorial_asset_exemple.background1)

```

```package
tutorial_asset_exemple=github:sbergeroncp/tutorial_asset_exemple
```

## Étape 2

Ajoute le bloc ``||variables:définir mySprite||`` (onglet ``||Sprites:Sprites||``) sous le bloc ``||scene:définir image d'arrière-plan||``.

Clique sur le carré gris et sélectionne l'avion qui pointe vers la gauche.

```blocks

scene.setBackgroundImage(tutorial_asset_exemple.screen_1)
let mySprite = sprites.create(img`
    ....ffffff.........ccc..
    ....ff22ccf.......cc4f..
    .....ffccccfff...cc44f..
    ....cc24442222cccc442f..
    ...c9b4422222222cc422f..
    ..c999b2222222222222fc..
    .c2b99111b222222222c22c.
    c222b111992222ccccccc22f
    f222222222222c222ccfffff
    .f2222222222442222f.....
    ..ff2222222cf442222f....
    ....ffffffffff442222c...
    .........f2cfffc2222c...
    .........fcc2ffffffff...
    ..........fc2ffff.......
    ...........fffff........
    `, SpriteKind.Player)

```

## Étape 3

Ajoute le bloc ``||sprites:définir la position||`` (onglet ``||Sprites:Sprites||``) sous le bloc ``||variables:définir mySprite||``.

Remplace la valeur ``||sprites:0||`` de gauche par ``||sprites:145||``.

Remplace la valeur ``||sprites:0||`` de droite par ``||sprites:10||``.

```blocks

scene.setBackgroundImage(tutorial_asset_exemple.screen_1)
let mySprite = sprites.create(img`
    ....ffffff.........ccc..
    ....ff22ccf.......cc4f..
    .....ffccccfff...cc44f..
    ....cc24442222cccc442f..
    ...c9b4422222222cc422f..
    ..c999b2222222222222fc..
    .c2b99111b222222222c22c.
    c222b111992222ccccccc22f
    f222222222222c222ccfffff
    .f2222222222442222f.....
    ..ff2222222cf442222f....
    ....ffffffffff442222c...
    .........f2cfffc2222c...
    .........fcc2ffffffff...
    ..........fc2ffff.......
    ...........fffff........
    `, SpriteKind.Player)
mySprite.setPosition(145, 10)

```

## Étape 4A

Ajoute le bloc ``||sprites:définir la vitesse||`` (onglet ``||Sprites:Sprites||``) sous le bloc ``||sprites:définir la position||``.

Remplace la valeur ``||sprites:50||`` de gauche par ``||sprites:-15||``.

Remplace la valeur ``||sprites:50||`` de droite par ``||sprites:0||``.

```blocks

scene.setBackgroundImage(tutorial_asset_exemple.screen_1)
let mySprite = sprites.create(img`
    ....ffffff.........ccc..
    ....ff22ccf.......cc4f..
    .....ffccccfff...cc44f..
    ....cc24442222cccc442f..
    ...c9b4422222222cc422f..
    ..c999b2222222222222fc..
    .c2b99111b222222222c22c.
    c222b111992222ccccccc22f
    f222222222222c222ccfffff
    .f2222222222442222f.....
    ..ff2222222cf442222f....
    ....ffffffffff442222c...
    .........f2cfffc2222c...
    .........fcc2ffffffff...
    ..........fc2ffff.......
    ...........fffff........
    `, SpriteKind.Player)
mySprite.setPosition(145, 10)
mySprite.setVelocity(-15, 0)

```

## Étape 4B

Ajoute le bloc ``||animation:animer||`` (onglet ``||animation:Animation||`` dans Avancé) sous le bloc ``||sprites:définir la vitesse||``.

Sélectionne les valeurs ci-dessous :

► ``||animation:animer||`` : ``||variables:mySprite||``

► ``||animation:trames||`` : appuie sur le carré vide pour ajouter une ressource et sélectionne l'animation correspondant à ton lutin dans l'onglet Galerie

► ``||animation:intervalle (ms)||`` : 200 

► ``||animation:en boucle||`` : activé

```blocks

scene.setBackgroundImage(tutorial_asset_exemple.screen_1)
let mySprite = sprites.create(img`
    ....ffffff.........ccc..
    ....ff22ccf.......cc4f..
    .....ffccccfff...cc44f..
    ....cc24442222cccc442f..
    ...c9b4422222222cc422f..
    ..c999b2222222222222fc..
    .c2b99111b222222222c22c.
    c222b111992222ccccccc22f
    f222222222222c222ccfffff
    .f2222222222442222f.....
    ..ff2222222cf442222f....
    ....ffffffffff442222c...
    .........f2cfffc2222c...
    .........fcc2ffffffff...
    ..........fc2ffff.......
    ...........fffff........
    `, SpriteKind.Player)
mySprite.setPosition(145, 10)
mySprite.setVelocity(-15, 0)

```

## Étape 5

Ajoute le bloc ``||sprites:définir projectile||`` (onglet ``||Sprites:Sprites||``) dans le bloc ``||controler:quand bouton A est appuyué||``.

Remplace la valeur ``||sprites:50||`` de gauche par ``||sprites:0||``.

La valeur ``||sprites:50||`` de droite demeure la même.

```blocks

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    projectile = sprites.createProjectileFromSprite(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . 2 1 2 . . . . . . 
        . . . . . . . 2 1 2 . . . . . . 
        . . . . . . . 2 1 2 . . . . . . 
        . . . . . . . 3 1 3 . . . . . . 
        . . . . . . 2 3 1 3 2 . . . . . 
        . . . . . . 2 1 1 1 2 . . . . . 
        . . . . . . 2 1 1 1 3 . . . . . 
        . . . . . . 3 1 1 1 3 . . . . . 
        . . . . . . 3 1 1 1 3 . . . . . 
        . . . . . . 3 1 1 1 3 . . . . . 
        . . . . . . 2 3 1 3 2 . . . . . 
        . . . . . . . 2 2 2 . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, mySprite, 0, 50)
})

```

## Étape 6

Crée une fonction (onglet ``||Functions:Fonctions||``) et donne-lui le nom Surprise.

Ajoute le bloc ``||animation:animer||`` (onglet ``||animation:Animation||`` dans Avancé) dans le bloc ``||functions:Surprise||``.

Sélectionne les valeurs ci-dessous :

► ``||animation:animer||`` : ``||variables:projectile||``

► ``||animation:trames||`` : appuie sur le carré vide pour ajouter une ressource et sélectionne l'animation correspondant à ton projectile dans l'onglet Galerie

► ``||animation:intervalle (ms)||`` : 200 

► ``||animation:en boucle||`` : désactivé

```blocks

function Surprise () {
    animation.runImageAnimation(
    projectile,
    [img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . 2 1 2 . . . . . . 
        . . . . . . . 2 1 2 . . . . . . 
        . . . . . . . 2 1 2 . . . . . . 
        . . . . . . . 3 1 3 . . . . . . 
        . . . . . . 2 3 1 3 2 . . . . . 
        . . . . . . 2 1 1 1 2 . . . . . 
        . . . . . . 2 1 1 1 3 . . . . . 
        . . . . . . 3 1 1 1 3 . . . . . 
        . . . . . . 3 1 1 1 3 . . . . . 
        . . . . . . 3 1 1 1 3 . . . . . 
        . . . . . . 2 3 1 3 2 . . . . . 
        . . . . . . . 2 2 2 . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `,img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . 2 3 3 3 3 3 2 . . . . 
        . . . . 3 1 1 1 1 1 1 1 3 . . . 
        . . . . 1 1 1 1 1 1 1 1 1 . . . 
        . . . 2 1 1 1 1 1 1 1 1 1 2 . . 
        . . . 2 3 1 1 1 1 1 1 3 3 2 . . 
        . . . . . . 2 2 2 2 2 . . . . . 
        `,img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . 4 4 4 4 4 . . . . . . 
        . . . 4 4 4 5 5 5 d 4 4 4 4 . . 
        . . 4 d 5 d 5 5 5 d d d 4 4 . . 
        . . 4 5 5 1 1 1 d d 5 5 5 4 . . 
        . 4 5 5 5 1 1 1 5 1 1 5 5 4 4 . 
        . 4 d d 1 1 5 5 5 1 1 5 5 d 4 . 
        . 4 5 5 1 1 5 1 1 5 5 d d d 4 . 
        . 2 5 5 5 d 1 1 1 5 1 1 5 5 2 . 
        . 2 d 5 5 d 1 1 1 5 1 1 5 5 2 . 
        . . 2 4 d d 5 5 5 5 d d 5 4 . . 
        . . . 2 2 4 d 5 5 d d 4 4 . . . 
        . . 2 2 2 2 2 4 4 4 2 2 2 . . . 
        . . . 2 2 4 4 4 4 4 4 2 2 . . . 
        . . . . . 2 2 2 2 2 2 . . . . . 
        `,img`
        . . . . 2 2 2 2 2 2 2 2 . . . . 
        . . . 2 4 4 4 5 5 4 4 4 2 2 2 . 
        . 2 2 5 5 d 4 5 5 5 4 4 4 4 2 . 
        . 2 4 5 5 5 5 d 5 5 5 4 5 4 2 2 
        . 2 4 d d 5 5 5 5 5 5 d 4 4 4 2 
        2 4 5 5 d 5 5 5 d d d 5 5 5 4 4 
        2 4 5 5 4 4 4 d 5 5 d 5 5 5 4 4 
        4 4 4 4 . . 2 4 5 5 . . 4 4 4 4 
        . . b b b b 2 4 4 2 b b b b . . 
        . b d d d d 2 4 4 2 d d d d b . 
        b d d b b b 2 4 4 2 b b b d d b 
        b d d b b b b b b b b b b d d b 
        b b d 1 1 3 1 1 d 1 d 1 1 d b b 
        . . b b d d 1 1 3 d d 1 b b . . 
        . . 2 2 4 4 4 4 4 4 4 4 2 2 . . 
        . . . 2 2 4 4 4 4 4 2 2 2 . . . 
        `,img`
        . . . . . . . . b b . . . . . . 
        . . . . . . . . b b . . . . . . 
        . . . b b b . . . . . . . . . . 
        . . b d d b . . . . . . . b b . 
        . b d d d b . . . . . . b d d b 
        . b d d b . . . . b b . b d d b 
        . b b b . . . . . b b . . b b . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . b b b d d d d d d b b b . . 
        . b d c c c b b b b c c d d b . 
        b d d c b . . . . . b c c d d b 
        c d d b b . . . . . . b c d d c 
        c b d d d b b . . . . b d d c c 
        . c c b d d d d b . c c c c c c 
        . . . c c c c c c . . . . . . . 
        `],
    200,
    false
    )
}
```

## Étape 7

Ajoute le bloc ``||functions:appel Surprise||`` (onglet ``||functions:Fonctions||``) dans le bloc ``||controler:quand bouton A est appuyué||``.

Remplace la valeur ``||controler:A||`` par ``||controler:B||``.

```blocks

controller.B.onEvent(ControllerButtonEvent.Pressed, function () {
    Surprise()
})
function Surprise () {
    animation.runImageAnimation(
    projectile,
    [img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . 2 1 2 . . . . . . 
        . . . . . . . 2 1 2 . . . . . . 
        . . . . . . . 2 1 2 . . . . . . 
        . . . . . . . 3 1 3 . . . . . . 
        . . . . . . 2 3 1 3 2 . . . . . 
        . . . . . . 2 1 1 1 2 . . . . . 
        . . . . . . 2 1 1 1 3 . . . . . 
        . . . . . . 3 1 1 1 3 . . . . . 
        . . . . . . 3 1 1 1 3 . . . . . 
        . . . . . . 3 1 1 1 3 . . . . . 
        . . . . . . 2 3 1 3 2 . . . . . 
        . . . . . . . 2 2 2 . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `,img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . 2 3 3 3 3 3 2 . . . . 
        . . . . 3 1 1 1 1 1 1 1 3 . . . 
        . . . . 1 1 1 1 1 1 1 1 1 . . . 
        . . . 2 1 1 1 1 1 1 1 1 1 2 . . 
        . . . 2 3 1 1 1 1 1 1 3 3 2 . . 
        . . . . . . 2 2 2 2 2 . . . . . 
        `,img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . 4 4 4 4 4 . . . . . . 
        . . . 4 4 4 5 5 5 d 4 4 4 4 . . 
        . . 4 d 5 d 5 5 5 d d d 4 4 . . 
        . . 4 5 5 1 1 1 d d 5 5 5 4 . . 
        . 4 5 5 5 1 1 1 5 1 1 5 5 4 4 . 
        . 4 d d 1 1 5 5 5 1 1 5 5 d 4 . 
        . 4 5 5 1 1 5 1 1 5 5 d d d 4 . 
        . 2 5 5 5 d 1 1 1 5 1 1 5 5 2 . 
        . 2 d 5 5 d 1 1 1 5 1 1 5 5 2 . 
        . . 2 4 d d 5 5 5 5 d d 5 4 . . 
        . . . 2 2 4 d 5 5 d d 4 4 . . . 
        . . 2 2 2 2 2 4 4 4 2 2 2 . . . 
        . . . 2 2 4 4 4 4 4 4 2 2 . . . 
        . . . . . 2 2 2 2 2 2 . . . . . 
        `,img`
        . . . . 2 2 2 2 2 2 2 2 . . . . 
        . . . 2 4 4 4 5 5 4 4 4 2 2 2 . 
        . 2 2 5 5 d 4 5 5 5 4 4 4 4 2 . 
        . 2 4 5 5 5 5 d 5 5 5 4 5 4 2 2 
        . 2 4 d d 5 5 5 5 5 5 d 4 4 4 2 
        2 4 5 5 d 5 5 5 d d d 5 5 5 4 4 
        2 4 5 5 4 4 4 d 5 5 d 5 5 5 4 4 
        4 4 4 4 . . 2 4 5 5 . . 4 4 4 4 
        . . b b b b 2 4 4 2 b b b b . . 
        . b d d d d 2 4 4 2 d d d d b . 
        b d d b b b 2 4 4 2 b b b d d b 
        b d d b b b b b b b b b b d d b 
        b b d 1 1 3 1 1 d 1 d 1 1 d b b 
        . . b b d d 1 1 3 d d 1 b b . . 
        . . 2 2 4 4 4 4 4 4 4 4 2 2 . . 
        . . . 2 2 4 4 4 4 4 2 2 2 . . . 
        `,img`
        . . . . . . . . b b . . . . . . 
        . . . . . . . . b b . . . . . . 
        . . . b b b . . . . . . . . . . 
        . . b d d b . . . . . . . b b . 
        . b d d d b . . . . . . b d d b 
        . b d d b . . . . b b . b d d b 
        . b b b . . . . . b b . . b b . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . b b b d d d d d d b b b . . 
        . b d c c c b b b b c c d d b . 
        b d d c b . . . . . b c c d d b 
        c d d b b . . . . . . b c d d c 
        c b d d d b b . . . . b d d c c 
        . c c b d d d d b . c c c c c c 
        . . . c c c c c c . . . . . . . 
        `],
    200,
    false
    )
}

```