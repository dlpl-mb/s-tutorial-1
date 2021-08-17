# TUTORIAL
# Der lachende Smiley

## Information @unplugged 
**Erklärung**
Der Smiley sollte froh UND/oder traurig aussehen.


![Button A oder B drücken](/static/mb/projects/smiley-buttons/sim.gif)

## Step 2 @fullscreen 
**Ereignis Schütteln**<br>

Positioniere einen Block ``||input:Wenn Knopf A gedrück||`` und teste ihn druch Drücken des Button **A**.

```blocks
input.onGesture(Gesture.Shake, function () {
    basic.showNumber(randint(0, 10))
})
## 
```