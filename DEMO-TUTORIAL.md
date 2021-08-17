# Der lachende Smiley

## Information @unplugged 

Der Smiley sollte froh oder traurig aussehen.
(Wie arbeiten die Button? [Schau dir das englische Video an.](https://youtu.be/t_Qujjd_38o)).

![Button A oder B drücken](/static/mb/projects/smiley-buttons/sim.gif)
<img width="200px" src="https://github.com/dlpl-mb/s-tutorial-1/blob/master/images/12t.gif?raw=1">
## Step 1 

Positioniere einen Block ``||input:Wenn Knopf A gedrück||`` und teste ihn druch Drücken des Button **A**.

```blocks
input.onButtonPressed(Button.A, () => { 
});
```

## Step 2 @fullscreen
(baa: @unplugged steht für Dialogfenster beim Tutorial, @fullscreen für offene Informationsfenster)
Place a ``||basic:Zeige LEDs||`` innerhalb von ``||input:Wenn Knopf A gedrückt||`` to display a smiley on the screen. Press the **A** button in the simulator to see the smiley.

```blocks
input.onButtonPressed(Button.A, () => { 
    basic.showLeds(`
        # # . # #
        # # . # #
        . . . . .
        # . . . #
        . # # # .`
        );
});
```

## Step 3

Add ``||input:on button pressed||`` and ``||basic:show leds||`` blocks to display a frowny when button **B** is pressed.

```blocks
input.onButtonPressed(Button.B, () => { 
    basic.showLeds(`
        # # . # #
        # # . # #
        . . . . .
        . # # # .
        # . . . #`
        );
});
```

## Step 4

Add a secret mode that happens when **A** and **B** are pressed together. For this case, add multiple ``||basic:show leds||`` blocks to create an animation.

```blocks
input.onButtonPressed(Button.AB, () => {
    basic.showLeds(`
        . . . . .
        # . # . .
        . . . . .
        # . . . #
        . # # # .
        `)
    basic.showLeds(`
        . . . . .
        . . # . #
        . . . . .
        # . . . #
        . # # # .
        `)    
})
```

## Step 5

If you have a @boardname@, connect it to USB and click ``|Download|`` to transfer your code. Press button **A** on your @boardname@. Try button **B** and then **A** and **B** together.

## Step 6

Nice! Now go and show it off to your friends!