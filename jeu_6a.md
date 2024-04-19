# Tutoriel 6

## @showdialog

Mon premier Shoot 'Em Up !

## Étape 1

Ajoute le bloc ``||scene:définir couleur d'arrière-plan||`` (onglet ``||scene:Scène||``) dans le bloc ``||loops:au démarrage||``.

Clique sur le carré gris une couleur.

```blocks
scene.setBackgroundColor(15)

```

## Étape 2

Ajoute le bloc ``||game:splash||`` (onglet ``||game:Jeu||``) sous le bloc ``||scene:définir couleur d'arrière-plan||``.

Écris le nom de ton jeu dans le bloc ``||game:splash||``.

```blocks

scene.setBackgroundColor(15)
game.splash("Gradius", "V")

```

## Étape 3

Ajoute le bloc ``||scene:démarrer effet||`` (onglet ``||scene:Scène||``) sous le bloc ``||game:splash||``.

Remplace la valeur ``||scene:confetti||`` par ``||scene:champ étoilé||``.

```blocks

scene.setBackgroundColor(15)
game.splash("Gradius", "V")
effects.starField.startScreenEffect()

```

## Étape 4

Ajoute le bloc ``||variables:définir mySprite||`` (onglet ``||sprites:Sprites||``) sous le bloc ``||scene:démarrer effet||``.

Renomme la valeur ``||variables:mySprite||`` par ``||variables:vaisseau||``.

Clique sur le carré gris et dessine un vaisseau spatial qui pointe vers le haut.

Regarde l'indice au besoin.

```blocks

scene.setBackgroundColor(15)
game.splash("Gradius", "V")
effects.starField.startScreenEffect()
let vaisseau = sprites.create(img`
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
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)

```

## Étape 5

Ajoute le bloc ``||scroller:déplacer avec les boutons||`` (onglet ``||scroller:Contrôleur||``) sous le bloc ``||variables:définir mySprite||``.

Remplace la valeur ``||variables:mySprite||`` par ``||variables:vaisseau||``.

Appuie sur le ``||scroller:+||`` pour afficher plus d'options.

Remplace les valeurs ``||scroller:100||`` par ``||scroller:125||``.

```blocks

scene.setBackgroundColor(15)
game.splash("Gradius", "V")
effects.starField.startScreenEffect()
let vaisseau = sprites.create(img`
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
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(vaisseau, 125, 125)

```

## Étape 6

Ajoute le bloc ``||sprites:rester à l'écran||`` (onglet ``||sprites:Sprites||``) sous le bloc ``||scroller:déplacer avec les boutons||``.

Remplace la valeur ``||variables:mySprite||`` par ``||variables:vaisseau||``.

Assure-toi que le bloc soit ``||animation:activé||``.

```blocks

scene.setBackgroundColor(15)
game.splash("Gradius", "V")
effects.starField.startScreenEffect()
let vaisseau = sprites.create(img`
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
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(vaisseau, 125, 125)
vaisseau.setStayInScreen(true)

```

## Étape 7

Ajoute les blocs ``||info:définir score||``, ``||info:définir vie||`` et ``||info:démarrer compte à rebours||`` (onglet ``||info:Info||``) sous le bloc ``||sprites:rester à l'écran||``.

Sélectionne les valeurs ci-dessous :

► ``||info:définir score||`` : ``||info:0||``

► ``||info:définir vie||`` : ``||info:3||``

► ``||info:démarrer compte à rebours||`` : ``||info:60||`` 

```blocks

scene.setBackgroundColor(15)
game.splash("Gradius", "V")
effects.starField.startScreenEffect()
let vaisseau = sprites.create(img`
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
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(vaisseau, 125, 125)
vaisseau.setStayInScreen(true)
info.setScore(0)
info.setLife(3)
info.startCountdown(60)

```

## Étape 8

Ajoute le bloc ``||music:définir le volume||`` (onglet ``||music:Musique||``) sous le bloc ``||info:démarrer compte à rebours||``.

Remplace la valeur ``||music:20||`` par ``||music:255||``.

```blocks

scene.setBackgroundColor(15)
game.splash("Gradius", "V")
effects.starField.startScreenEffect()
let vaisseau = sprites.create(img`
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
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(vaisseau, 125, 125)
vaisseau.setStayInScreen(true)
info.setScore(0)
info.setLife(3)
info.startCountdown(60)
music.setVolume(255)

```

## Étape 9

Glisse le bloc ``||game:quand||`` (onglet ``||game:Jeu||``) dans la zone de programmation.

Remplace la valeur ``||game:500||`` par ``||game:1000||``.

```blocks

game.onUpdateInterval(5000, function () {
	
})

```

## Étape 10

Ajoute le bloc ``||variables:définir projectile||`` (onglet ``||sprites:Sprites||``) dans le bloc ``||game:quand||``.

Renomme la valeur ``||variable:projectile||`` par ``||variable:alpha||``.

Clique sur le carré gris pour sélectionner un lutin dans la Galerie.

Remplace la valeur ``||sprites:50||`` de gauche par ``||sprites:0||``.

La valeur ``||sprites:50||`` de droite demeure la même.

```blocks

let alpha: Sprite = null
game.onUpdateInterval(1000, function () {
    alpha = sprites.createProjectileFromSide(img`
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
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, 0, 50)
})

```

## Étape 11

Ajoute le bloc ``||sprites:définir x||`` (onglet ``||sprites:Sprites||``) sous le bloc ``||variables:définir alpha||``.

Remplace la valeur ``||variable:mySprite||`` par ``||variable:alpha||``.

Remplace la valeur ``||sprites:0||`` par le bloc ``||math:choisir aléatoirement entre||``.

Remplace la valeur ``||math:0||`` par ``||math:5||``.

Remplace la valeur ``||math:10||`` par ``||math:155||``.

```blocks

let alpha: Sprite = null
game.onUpdateInterval(1000, function () {
    alpha = sprites.createProjectileFromSide(img`
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
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, 0, 50)
    alpha.x = randint(5, 155)
})

```

## Étape 12

Ajoute le bloc ``||sprites:définir le type||`` (onglet ``||sprites:Sprites||``) sous le bloc ``||sprites:définir x||``.

Remplace la valeur ``||variable:mySprite||`` par ``||variable:alpha||``.

** Attention tu dois créer une nouvelle valeur pour la prochaine étape! **

Remplace la valeur ``||sprites:Player||`` par la valeur ``||sprites:ennemi1||``.

```blocks

namespace SpriteKind {
    export const ennemi1 = SpriteKind.create()
}
let alpha: Sprite = null
game.onUpdateInterval(1000, function () {
    alpha = sprites.createProjectileFromSide(img`
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
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, 0, 50)
    alpha.x = randint(5, 155)
    alpha.setKind(SpriteKind.ennemi1)
})


```

## Étape 13

Dupplique le bloc ``||game:quand mise à jour du jeu chaque 1000 ms||``.

Remplace la valeur ``||game:1000||`` par ``||game:2500||``.

```blocks

namespace SpriteKind {
    export const ennemi1 = SpriteKind.create()
}
let alpha: Sprite = null
game.onUpdateInterval(2500, function () {
    alpha = sprites.createProjectileFromSide(img`
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
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, 0, 50)
    alpha.x = randint(5, 155)
    alpha.setKind(SpriteKind.ennemi1)
})


```

## Étape 14

Pour le bloc ``||variables:définir alpha||`` :

Renomme la valeur ``||variable:alpha||`` par ``||variable:beta||``.

Clique sur le carré gris pour sélectionner un lutin dans la Galerie.

La valeur ``||sprites:0||`` de gauche demeure la même.

Remplace la valeur ``||sprites:50||`` par ``||sprites:75||``.

```blocks

namespace SpriteKind {
    export const ennemi2 = SpriteKind.create()
}
let beta: Sprite = null
game.onUpdateInterval(1000, function () {
    beta = sprites.createProjectileFromSide(img`
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
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, 0, 75)
    beta.x = randint(5, 155)
    beta.setKind(SpriteKind.ennemi2)
})


```

## Étape 15

Pour le bloc ``||sprites:définir x||`` :

Remplace la valeur ``||variable:alpha||`` par ``||variable:beta||``.

Les valeurs ``||math:5||`` et ``||math:155||`` demeurent les mêmes.

```blocks

namespace SpriteKind {
    export const ennemi2 = SpriteKind.create()
}
let beta: Sprite = null
game.onUpdateInterval(2500, function () {
    beta = sprites.createProjectileFromSide(img`
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
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, 0, 75)
    beta.x = randint(5, 155)
    beta.setKind(SpriteKind.ennemi2)
})

```

## Étape 16

Pour le bloc ``||sprites:définir le type||`` :

Remplace la valeur ``||variable:alpha||`` par ``||variable:beta||``.

** Attention tu dois créer une nouvelle valeur pour la prochaine étape! **

Remplace la valeur ``||sprites:ennemi1||`` par la valeur ``||sprites:ennemi2||``.

```blocks

namespace SpriteKind {
    export const ennemi2 = SpriteKind.create()
}
let beta: Sprite = null
game.onUpdateInterval(2500, function () {
    beta = sprites.createProjectileFromSide(img`
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
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, 0, 75)
    beta.x = randint(5, 155)
    beta.setKind(SpriteKind.ennemi2)
})

```

## Étape 17

Dupplique le bloc ``||game:quand mise àjour du jeu chaque 1000 ms||``.

Remplace la valeur ``||game:1000||`` par ``||game:5000||``.

```blocks

namespace SpriteKind {
    export const ennemi1 = SpriteKind.create()
}
let alpha: Sprite = null
game.onUpdateInterval(5000, function () {
    alpha = sprites.createProjectileFromSide(img`
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
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, 0, 50)
    alpha.x = randint(5, 155)
    alpha.setKind(SpriteKind.ennemi1)
})

```

## Étape 18

Pour le bloc ``||variables:définir alpha||`` :

Renomme la valeur ``||variable:alpha||`` par ``||variable:charlie||``.

Clique sur le carré gris pour sélectionner un lutin dans la Galerie.

La valeur ``||sprites:0||`` de gauche demeure la même.

Remplace la valeur ``||sprites:50||`` par ``||sprites:100||``.

```blocks

namespace SpriteKind {
    export const ennemi3 = SpriteKind.create()
}
let charlie: Sprite = null
game.onUpdateInterval(5000, function () {
    charlie = sprites.createProjectileFromSide(img`
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
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, 0, 100)
    charlie.x = randint(5, 155)
    charlie.setKind(SpriteKind.ennemi3)
})

```

## Étape 19

Pour le bloc ``||sprites:définir x||`` :

Remplace la valeur ``||variable:beta||`` par ``||variable:charlie||``.

Les valeurs ``||math:5||`` et ``||math:155||`` demeurent les mêmes.

```blocks

namespace SpriteKind {
    export const ennemi3 = SpriteKind.create()
}
let charlie: Sprite = null
game.onUpdateInterval(5000, function () {
    charlie = sprites.createProjectileFromSide(img`
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
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, 0, 100)
    charlie.x = randint(5, 155)
    charlie.setKind(SpriteKind.ennemi3)
})

```

## Étape 20

Pour le bloc ``||sprites:définir le type||`` :

Remplace la valeur ``||variable:alpha||`` par ``||variable:charlie||``.

** Attention tu dois créer une nouvelle valeur pour la prochaine étape! **

Remplace la valeur ``||sprites:ennemi1||`` par la valeur ``||sprites:ennemi3||``.

```blocks

namespace SpriteKind {
    export const ennemi3 = SpriteKind.create()
}
let charlie: Sprite = null
game.onUpdateInterval(5000, function () {
    charlie = sprites.createProjectileFromSide(img`
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
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, 0, 100)
    charlie.x = randint(5, 155)
    charlie.setKind(SpriteKind.ennemi3)
})

```

## Étape 21

Glisse le bloc ``||scroller:quand bouton A est pressé||`` (onglet ``||scroller:Contrôleur||``) dans la zone de programmation.

Ajoute le bloc ``||variables:définir projectile||`` dans le bloc ``||scroller:quand bouton A est pressé||``.

Clique sur le carré gris et dessine un petit missile qui pointe vers le haut.

```blocks

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    let mySprite: Sprite = null
    projectile = sprites.createProjectileFromSprite(img`
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
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, mySprite, 50, 50)
})

```

## Étape 22

Continue à modifier le bloc ``||variables:définir projectile||``.

Remplace la valeur ``||variables:mySprite||`` par ``||variables:vaisseau||``.

Remplace la valeur ``||sprites:50||`` de gauche par ``||sprites:0||``.

Remplace la valeur ``||sprites:50||`` de droite par ``||sprites:-150||``.

```blocks

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    projectile = sprites.createProjectileFromSprite(img`
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
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, vaisseau, 0, -150)
})
```

## Étape 23

Ajoute le bloc ``||music:play jusqu'à la fin|`` (onglet ``||music:Musique||``) sous le bloc ``||variables:définir projectile||``.

Remplace la valeur ``||music:sound ba ding|`` par ``||music:sound zapper|``.

Remplace la valeur ``||music:jusqu'à la fin|`` par ``||music:in background|`` (trad. : en arrière-plan).

```blocks

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    projectile = sprites.createProjectileFromSprite(img`
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
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, vaisseau, 0, -150)
    music.play(music.melodyPlayable(music.zapped), music.PlaybackMode.InBackground)
})

```

## Étape 24

Dupplique le bloc ``||scroller:quand bouton A est pressé||``.

Remplace la valeur ``||scroller:A||`` par ``||scroller:B||``.

```blocks

controller.B.onEvent(ControllerButtonEvent.Pressed, function () {
    projectile = sprites.createProjectileFromSprite(img`
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
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, vaisseau, 0, -150)
    music.play(music.melodyPlayable(music.zapped), music.PlaybackMode.InBackground)
})

```

## Étape 25

Modifie le contenu du bloc ``||scroller:quand bouton B est pressé||``.

Clique sur le carré gris et dessine plus gros missile qui pointe vers le haut.

La valeur de ``||sprites:0||`` de gauche demeure la même.

Remplace la valeur ``||sprites:-150||`` par ``||sprites:-75||``.

Remplace la valeur ``||music:sound zapped||`` par ``||music:sound pew pew||``.

```blocks

controller.B.onEvent(ControllerButtonEvent.Pressed, function () {
    projectile = sprites.createProjectileFromSprite(img`
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
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, vaisseau, 0, -75)
    music.play(music.melodyPlayable(music.pewPew), music.PlaybackMode.InBackground)
})

```