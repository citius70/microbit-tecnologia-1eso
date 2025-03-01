# Sonido de pájaro

## Paso 1

Reproduce el sonido de un pájaro.

```blocks
basic.forever(function () {
    music.play(music.createSoundExpression(
    WaveShape.Sine,
    input.acceleration(Dimension.X) * 50,
    input.acceleration(Dimension.Y) * 50,
    randint(150, 255),
    255,
    randint(80, 100),
    SoundExpressionEffect.None,
    InterpolationCurve.Linear
    ), music.PlaybackMode.UntilDone)
})
```
