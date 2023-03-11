# Microbit Schere-Stein-Papier 

``` blocks
basic.forever(function () {
basic.showIcon(IconNames.Heart)
basic.pause(20)
basic.showIcon(IconNames.SmallHeart)
})
```

## Fragen über Fragen
Bibi oder ConCrafter? Pizza oder doch lieber Burger zum Mittagessen? Chillen oder endlich einmal 
den neuen Kletterpark erkunden? Und wer ist nun eigentlich heute der "Lauch", der das Geschirr 
abwaschen muss: du oder deine Schwester? 

## Problemstellung: Wer übernimmt die Entscheidung ? (1)
Eine gefühlte Ewigkeit diskutieren du und deine Freunde, 
deine Geschwister oder deine Eltern und niemand möchte nachgeben. Eine gemeinsame Entscheidung? 
Von wegen, für beide Möglichkeiten sprechen wirklich gute Gründe, die ihr euch auch lautstark
um die Ohren haut.

## Problemstellung: Wer übernimmt die Entscheidung ? (2)
Und nun? Schmollen? Das funktioniert schon lange nicht mehr und ist ja eigentlich, wenn wir ehrlich
sind, verlorene Zeit. Letztendlich muss ja doch eine Entscheidung getroffen werden. Münzenwerfen? 
Schade um die Münze! Schere, Stein, Papier? Eigentlich eine gute Lösung, wenn da nicht die vielen 
Schummelversuche wären…

## Hier kommt die gute Nachricht! 
Es gibt endlich eine Lösung für das Entscheidungsfindungsproblem: 
Du baust dein eigenes schummelsicheres No-cheat-micro:bit-Schere-Stein-Papier als stylisches Wearable!
Die Regeln kennen wir alle: Schere schlägt Papier, Papier schlägt Stein und Stein schlägt Schere – 
aber dank des *micro:bits völlig schummelfrei*!

## Aufgabenstellung 
Programmiere den No-cheat-micro:bit-Schere-Stein-Papier Wearable: Jedesmal wenn du den Microbit shakest 
(wackelst), wird Schere, Stein oder Papier auf dem 5x5 LED-Display angezeigt. Gehe nun wie folgt vor: 

1. Wenn du glaubst es selbst zu schaffen, dann probiere es einmal selbständig. 
2. Wenn nicht, gehe zum nächsten Schritt und folge der Anleitung. 

PS: Das Band des Wearables, könnt ihr im Werkunterricht oder zu Hause selbst basteln, denn ihr dürft 
diesen behalten :-). 

## Schritt 1: Shaken 
Jedesmal wenn wir den Microbit schütteln, muss dieser darauf reagierne. Deshalb benötigen zum Auslösen 
folgenden Codeblock: 

``` blocks
input.onGesture(Gesture.Shake, function () {

})

```

## Schritt 2: Zufällige Schere (1), Stein (2)ODER Papier (3) wählen  

Der Microbit muss zufällig zwischen Papier, Schere oder Stein wählen. Da er diese Namen nicht so einfach
zufällig auswählen kann, sondern nur Zahlen kennt, müssen wir eine andere Bennenung finden. Deswegen findne wir
eine neue Bennung: 
- `Papier` ist ab jetzt 1. 
- `Stein` ist ab jetzt 2. 
- `Schere` ist ab jetzt 3.


 
``` blocks
input.onGesture(Gesture.Shake, function () {
    hand = randint(1, 3)
    }
```

## Schritt 3: Wenn 

``` blocks
input.onGesture(Gesture.Shake, function () {
    hand = randint(1, 3)
    if (hand == 1) {
        basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
})

```



``` blocks
input.onGesture(Gesture.Shake, function () {
    hand = randint(1, 3)
    if (hand == 1) {
        basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
    } else if (hand == 2) {
        basic.showLeds(`
            . . . . .
            . # # # .
            . # # # .
            . # # # .
            . . . . .
            `)
    } else {
        basic.showLeds(`
            # # . . #
            # # . # .
            . . # . .
            # # . # .
            # # . . #
            `)
    }
})


## Finale Lösung
![A rendered view of the blocks](https://github.com/bdornauer/microbit-schere-stein-papier/raw/master/.github/makecode/blocks.png)
[Link zur Quelle](https://microbit.eeducation.at/wiki/SchereSteinPapier)