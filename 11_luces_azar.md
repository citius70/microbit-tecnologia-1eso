# Luces al azar

# Paso 1

```blocks
let numeroLeds = 0
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 5; index++) {
        numeroLeds = randint(0, 25)
        for (let index = 0; index < numeroLeds; index++) {
            led.plot(randint(0, 5), randint(0, 5))
        }
        music.play(music.tonePlayable(randint(131, 998), music.beat(BeatFraction.Whole)), music.PlaybackMode.UntilDone)
        basic.pause(500)
        basic.clearScreen()
    }
})
```
