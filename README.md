# Micro:bit Schere-Stein-Papier 

##Introduction @unplugged 

Bibi oder ConCrafter? Pizza oder doch lieber Burger zum Mittagessen? Chillen oder endlich einmal 
den neuen Kletterpark erkunden? Und wer ist nun eigentlich heute der "Lauch", der das Geschirr 
abwaschen muss: du oder doch jemand anderes? 

Eine gefühlte Ewigkeit diskutieren du und deine Freunde, 
deine Geschwister oder deine Eltern und niemand möchte nachgeben. Eine gemeinsame Entscheidung? 
Von wegen, für beide Möglichkeiten sprechen wirklich gute Gründe, die ihr euch auch lautstark
um die Ohren haut.

✂️🪨 📃 Und nun? Schmollen? Das funktioniert schon lange nicht mehr und ist ja eigentlich, wenn wir ehrlich
sind, verlorene Zeit. Letztendlich muss ja doch eine Entscheidung getroffen werden. Münzenwerfen? 
Schade um die Münze! Schere, Stein, Papier? Eigentlich eine gute Lösung, wenn da nicht die vielen 
Schummelversuche wären…

## Hier kommt die gute Nachricht! 
Es gibt endlich eine Lösung für das Entscheidungsfindungsproblem: 
Du baust dein eigenes schummelsicheres No-cheat-micro:bit-Schere-Stein-Papier als stylisches Wearable!
Die Regeln kennen wir alle: Schere schlägt Papier, Papier schlägt Stein und Stein schlägt Schere – 
aber dank des *micro:bits völlig schummelfrei*!

## Aufgabenstellung 
Programmiere den No-cheat-micro:bit-Schere-Stein-Papier Wearable: Jedesmal wenn du den Micro:bit schüttelst, 
wird Schere, Stein oder Papier auf dem 5x5 LED-Display angezeigt. Gehe nun wie folgt vor: 

1. Wenn du glaubst es selbst zu schaffen, dann probiere es einmal selbständig. 
2. Wenn du nicht weiterkommst bzw. eine Hilfestellung benötigst, gehe zum nächsten Schritt und folge der Anleitung. 

PS: Das Band des Wearables, könnt ihr z.B. im Werkunterricht oder zu Hause selbst basteln :-). 

## Schritt 1: Shaken 
Jedesmal wenn du den Micro:bit schüttelst, muss dieser darauf reagieren. Deshalb benötigst du als Eingabe
einen Codeblock, der auslöst wenn du ihn schüttelst. 

```ghost
input.onGesture(Gesture.Shake, function () {

})

```

## Schritt 2: Zufällige Schere (1), Stein (2) ODER Papier (3) wählen  

Der Micro:bit muss zufällig zwischen Papier, Schere oder Stein wählen. Da der Micro:bit diese Namen nicht so einfach
zufällig auswählen kann, sondern nur Zahlen kennt, müssen wir eine andere Bennenung finden. Deswegen legen wir
folgende Bennungen fest:
- Papier ist ab jetzt 1.
- Stein ist ab jetzt 2.
- Schere ist ab jetzt 3.
Erstelle eine Variable, in der du einen Wert zwischenspeicherst. Dieser Wert soll zufällig von 1 bis 3 gewählt werden. 

```ghost
input.onGesture(Gesture.Shake, function () {
    hand = randint(1, 3)
    }
```

## Schritt 3: Fall - Papier (=1) gewählt 
Nun müssen wir für den ersten Fall Papier, eine Grafik auf dem 5x5 LED-Grid anzeigen. Dazu gehen wir wie folgt vor:

Wir müssen zunächst vergleichen, ob Papier auch wirklich Papier ist. Das bedeutet, wir vergleichen den zufällig gewählten Wert
der Variable ob dieser gleich 1 ist. Wenn dies zutrifft (WAHR), soll auf dem Display eine dazu passende Grafik angezeigt werden. 

```ghost
input.onGesture(Gesture.Shake, function () {
    hand = randint(1, 3)
    if (hand == 1) {
        basic.showLeds(`
            # # # # #
            # # # # #
            # # # # #
            # # # # #
            # # # # #
            `)
})
```
## Schritt 4: Nun müssen nur noch die Fälle Stein (=2) und Schere (=3) umsetzen
Gleich wie beim vorherigen Fall, müssen wir noch den Fall Stein überprüfen. Dazu erweitern wir durch
**zweimaliges** Drücken auf + am Ende des `wenn ... dann` - Blocks die neuen Fälle. Gleich wie beim vorherigen Schritt, müssen
wir überprüfen, ob der Wert der Variable 2 ist. Stelle das ganze auf dem Display dar. 

Beim letzten Fall (=3) müssen wir keine Überprüfung des Wertes der Variable vornehmen, da dies immer der Fall ist, wenn
die Fälle Papier (=1) und Schere (=2) bereits überprüft wurden und nicht zugetroffen sind.

```ghost
input.onGesture(Gesture.Shake, function () {
    hand = randint(1, 3)
    if (hand == 1) {
        basic.showLeds(`
            # # # # #
            # # # # #
            # # # # #
            # # # # #
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
```
## Gratuliere du hast das Ende ereicht. 

Gratuliere du hast die Aufgabe gelöst 👍👍👍👍 Jetzt kannst du selber weiter arbeiten.
- Passe die Darstellungen von Schere, Stein und Papier an. 
- Erweitere Schere-Stein-Papier, um Stein-Papier-Schere-Echse-Spock 
[BigbangTheory](https://bigbangtheory.fandom.com/de/wiki/Stein,_Papier,_Schere,_Echse,_Spock)
- Erstelle ein Cheat-Schere-Stein Papier, wo du durch Drücken des Knopfes A immer auf den Fall Stein kommst. 
- ODER Überlege dir selbst etwas neus
- ODER du schaust auf [Microbit-Wiki](https://microbit.eeducation.at/wiki/Hauptseite) vorbei. 

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
