# Tutoriel 2

## @showdialog

Programme un lutin pour qu'il se déplace sur l'écran.

## Étape 1

Ajoute le bloc ``||scene:définir la couleur d'arrière-plan||`` (onglet ``||scene:Scène||``) dans le bloc ``||loops:au démarrage||``.

Choisis une couleur.

```blocks

scene.setBackgroundColor(15)

```

## Étape 2

Ajoute le bloc ``||variables:définir mySprite||`` (onglet ``||Sprites:Sprites||``) sous le bloc ``||scene:définir la couleur d'arrière-plan||``.

Choisis un lutin dans la Galerie.

```blocks

scene.setBackgroundColor(15)
let mySprite = sprites.create(img`
    . . f f f . . . . . . . . f f f 
    . f f c c . . . . . . f c b b c 
    f f c c . . . . . . f c b b c . 
    f c f c . . . . . . f b c c c . 
    f f f c c . c c . f c b b c c . 
    f f c 3 c c 3 c c f b c b b c . 
    f f b 3 b c 3 b c f b c c b c . 
    . c b b b b b b c b b c c c . . 
    . c 1 b b b 1 b b c c c c . . . 
    c b b b b b b b b b c c . . . . 
    c b c b b b c b b b b f . . . . 
    f b 1 f f f 1 b b b b f c . . . 
    f b b b b b b b b b b f c c . . 
    . f b b b b b b b b c f . . . . 
    . . f b b b b b b c f . . . . . 
    . . . f f f f f f f . . . . . . 
    `, SpriteKind.Player)

```

## Étape 3

Ajoute le bloc ``||scroller:déplacer avec les boutons||`` (onglet ``||scroller:Contrôleur||``) sous le bloc ``||Sprites:définir mySprite||``.

```blocks

scene.setBackgroundColor(15)
let mySprite = sprites.create(img`
    . . f f f . . . . . . . . f f f 
    . f f c c . . . . . . f c b b c 
    f f c c . . . . . . f c b b c . 
    f c f c . . . . . . f b c c c . 
    f f f c c . c c . f c b b c c . 
    f f c 3 c c 3 c c f b c b b c . 
    f f b 3 b c 3 b c f b c c b c . 
    . c b b b b b b c b b c c c . . 
    . c 1 b b b 1 b b c c c c . . . 
    c b b b b b b b b b c c . . . . 
    c b c b b b c b b b b f . . . . 
    f b 1 f f f 1 b b b b f c . . . 
    f b b b b b b b b b b f c c . . 
    . f b b b b b b b b c f . . . . 
    . . f b b b b b b c f . . . . . 
    . . . f f f f f f f . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(mySprite)

```

## Étape 4

Ajoute le bloc ``||animation:animer mySprite||`` (onglet ``||animation:Animation||`` dans Avancé) sous le bloc ``||scroller:déplacer avec les boutons||``.

Sélectionne les valeurs ci-dessous :

► ``||animation:animer||`` : ``||variables:mySprite||``

► ``||animation:trames||`` : appuie sur le carré vide pour ajouter une ressource et sélectionne l'animation correspondant à ton lutin dans l'onglet Galerie

► ``||animation:intervalle (ms)||`` : 500 

► ``||animation:en boucle||`` : activé

```blocks

scene.setBackgroundColor(15)
let mySprite = sprites.create(img`
    . . f f f . . . . . . . . f f f 
    . f f c c . . . . . . f c b b c 
    f f c c . . . . . . f c b b c . 
    f c f c . . . . . . f b c c c . 
    f f f c c . c c . f c b b c c . 
    f f c 3 c c 3 c c f b c b b c . 
    f f b 3 b c 3 b c f b c c b c . 
    . c b b b b b b c b b c c c . . 
    . c 1 b b b 1 b b c c c c . . . 
    c b b b b b b b b b c c . . . . 
    c b c b b b c b b b b f . . . . 
    f b 1 f f f 1 b b b b f c . . . 
    f b b b b b b b b b b f c c . . 
    . f b b b b b b b b c f . . . . 
    . . f b b b b b b c f . . . . . 
    . . . f f f f f f f . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(mySprite)
animation.runImageAnimation(
mySprite,
[img`
    f f f . . . . . . . . f f f . . 
    c b b c f . . . . . . c c f f . 
    . c b b c f . . . . . . c c f f 
    . c c c b f . . . . . . c f c f 
    . c c b b c f . c c . c c f f f 
    . c b b c b f c c 3 c c 3 c f f 
    . c b c c b f c b 3 c b 3 b f f 
    . . c c c b b c b 1 b b b 1 c . 
    . . . c c c c b b 1 b b b 1 c . 
    . . . . c c b b b b b b b b b c 
    . . . . f b b b b c 1 f f 1 b c 
    . . . c f b b b b f 1 f f 1 f f 
    . . c c f b b b b f 2 2 2 2 f f 
    . . . . f c b b b b 2 2 2 2 f . 
    . . . . . f c b b b b b b f . . 
    . . . . . . f f f f f f f . . . 
    `,img`
    . . . . . . . . . . . f f f . . 
    f f f . . . . . . . . c c f f f 
    c b b c f . . . c c . c c c f f 
    . c b b b f f c c 3 c c 3 c f f 
    . c c c b b f c b 3 c b 3 c f f 
    . c c b c b f c b b b b b b c f 
    . c b b c b b c b 1 b b b 1 c c 
    . c b c c c b b b b b b b b b c 
    . . c c c c c b b c 1 f f 1 b c 
    . . . c f b b b b f 1 f f 1 f c 
    . . . c f b b b b f f f f f f f 
    . . c c f b b b b f 2 2 2 2 f f 
    . . . . f c b b b 2 2 2 2 2 f . 
    . . . . . f c b b b 2 2 2 f . . 
    . . . . . . f f f f f f f . . . 
    . . . . . . . . . . . . . . . . 
    `,img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . c c . c c . . . 
    . . . . . . c c c 3 c c 3 f . . 
    . . . . . c c c b 3 c b 3 c f . 
    . . . . f f b b b b b b b b c f 
    . . . . f f b b b 1 b b b 1 c c 
    . . . f f f c b b b b b b b b c 
    . . . f f f f b b c 1 f f 1 b c 
    . . . b b b c c b f 1 f f 1 f f 
    . . . c c c c f b f f f f f f f 
    . . c c c b b f b f 2 2 2 2 f f 
    . . . c b b c c b 2 2 2 2 2 f . 
    . . c b b c c f f b 2 2 2 f . . 
    . c c c c c f f f f f f f . . . 
    c c c c . . . . . . . . . . . . 
    `,img`
    . f f f . . . . . . . . f f f . 
    . c b b c f . . . . . . . c f f 
    . . c b b c f . . . . . . c c f 
    . . c c c b f . . . . . . . f c 
    . . c c b b f f . . . . . f f c 
    . . c b b c b f c c . c c f f f 
    . . c b c c b f c c c c c f f f 
    . . . c c c b c b 3 c c 3 c f . 
    . . . c c c c b b 3 c b 3 b c . 
    . . . . c c b b b b b b b b c c 
    . . . c f b b b 1 1 b b b 1 1 c 
    . . c c f b b b b b b b b b b f 
    . . . . f b b b b c b b b c b f 
    . . . . f c b b b 1 f f f 1 f . 
    . . . . . f c b b b b b b f . . 
    . . . . . . f f f f f f f . . . 
    `],
500,
true
)

```
