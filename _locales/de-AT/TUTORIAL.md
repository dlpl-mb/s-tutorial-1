# TUTORIAL: Ei und Löffel Spiel 


## Erstinformation @unplugged 
**Erklärung**

Sonja und Elias wollen das Ei und Löffel Spiel mit dem micro:bit durchführen und dafür ein Programm schreiben.
![Bild Loeffel_kreativ]

![Button A oder B drücken](/static/mb/projects/smiley-buttons/sim.gif)

## Step 2 @fullscreen 
**Ereignis beim Spielstart**

Stelle das Ei symbolisch als eine einzeln leuchtende LED in der Mitte der LED Matrix dar.
```blocks
let x = 2
let y = 2
```

Positioniere einen Block ``||input:Beim Start||`` und teste ihn druch Drücken des Button **A**.

```blocks
input.onGesture(Gesture.Shake, function () {
    basic.showNumber(randint(0, 10))
})
```

```block
    basic.showIcon(IconNames.Heart)

```


## schritt 3 @fullscreen
**Ereignis dauerhaft**

Damit das Ei als mittlere Koordinate auf der LED Matrix leuchtet, muss die angegebene LED mithilfe der entsprechenden X und Y-Koordinate eingeschaltet werden.
In einer Endlosschleife frage ich den Wert der Bewegungsänderung in Richtung X- und Y-Achse ab.

```block
    basic.showIcon(IconNames.Heart)

```
```blocks
    basic.forever(function () {
    led.plot(x, y)
    accX = input.acceleration(Dimension.X)
    accY = input.acceleration(Dimension.Y)
```

## schritt 4 

**Ereignis dauerhaft**

Die leuchtende LED, die das Ei darstellt, darf sich nicht außerhalb der LED Matrix bewegen. Die X und Y-Koordinaten dürfen nur Werte von 0 bis 4 annehmen. Mithilfe von Bedingungen im Zusammenspiel mit dem Bewegungssensor wird die jeweilige Kipprichtung des micro:bits dauerhaft in der Schleife überprüft und die entsprechende Änderung der Variablen festgelegt.

```blocks
   basic.forever(function () {
   if (accX < -200 && x > 0) {
        x += -1
    } else if (accX > 200 && x < 4) {
        x += 1
    }
    if (accY < -200 && y > 0) {
        y += -1
    } else if (accY > 200 && y < 4) {
        y += 1
    }
```

## schritt 5 

**Tipps**

* Für die Bedingung musst du dir auch überlegen, wie rasch und sensibel der micro:bit bei Bewegung reagieren soll. Der vorgeschlagene Zahlenwert beträgt in diesem Beispiel 200.
* Lade dein fertiges Programm auf deinen micro:bit, klebe das Battieripack mit einem Doppelklebeband auf einen Löffel und gestalte den micro:bit als Ei. Die LED Matrix soll dabei sichtbar sein.
* Probiere das Ei und Löffel Spiel zuerst mit Ei und Löffel aus, verwende danach den micor:bit für dieses Bewegungsspiel. Vergleiche die Ergebnisse und experimentiere.
* Gestalte einen Team Bewerb in der Klasse, probiere das Spiel mit verschiedenen Variationen aus. Führe einen Staffellauf mit Eiübergabe (micro:bit Übergabe) und zwei Wettbewerbsteams durch.
<img width="200px" src="https://github.com/dlpl-mb/s-tutorial-1/blob/master/images/12t.gif?raw=1">