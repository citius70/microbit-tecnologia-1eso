# Medidor de nivel de luz

## Introducción @unplugged

Este programa utiliza el **sensor de luz** (LDR) del @boardname@ para:

* visualizar gráficamente el **nivel de luz** ambiental,
* crear una **alarma** que se accione cuando la *luz ambiental disminuya*.

![ldr](/static/Luz.png)


## Paso 1: Trazar el nivel de luz en una gráfica

Dentro del bloque ``||basic:para siempre||`` vamos a  ``||led:trazar un gráfico de barras||`` que muestre el nivel de  ``||input:nivel de luz||``. 

El sensor de luz del @boardname@ nos devuelve el valor:

* 0 (mínimo) cuando se encuentra en total oscuridad,

* 255 (máximo) cuando la luz ambiental es máxima.

Por ello, establece el límite de la grafica en 255 para que coincida con el valor máximo medido por el sensor.

```blocks
basic.forever(function () {
    led.plotBarGraph(
    input.lightLevel(),
    255
    )
    }
})
```

Mira el simulador y observa como cambia el gráfico de barras mientras ajustas el control del nivel de luz.

## Paso 2: Mostrar la lectura como número

Vamos a mostrar el nivel de luz en números (de 0 a 255) cuando pulsemos el botón ``|A|``.

Añade el bloque condicional ``||logic: si||`` con la condición ``||input: botón A presionado||`` 

Cuando esto ocurra (el presionar A) se debe ``||basic: mostrar número (nivel de luz)||``

```blocks
basic.forever(function () {
    led.plotBarGraph(
    input.lightLevel(),
    255
    )
    if (input.buttonIsPressed(Button.A)) {
        basic.showNumber(input.lightLevel())
    }
})
```

## Paso 3: Establecer una alarma cuando oscurezca 🌃

Por último, cuando el nivel de luz sea menor a un valor , sonará una alarma 🔊.

Para ello, añade otro bloque ``||logic: si <  >  entonces||`` en el que lo completarás con la condición ``||input: lightLevel() < 50||``.

Cuando el nivel de luz sea menor que 50, entonces debe sonar una melodía ``||music: reproduce secuencia (tono Sol alto durante 1 pulso) hasta que termine||``.

Además, ``||logic: si no ||`` se cumple la condición, es decir, el nivel de luz es mayor que 50, ``||music: para todos los sonidos||``.

```blocks
basic.forever(function () {
    led.plotBarGraph(
    input.lightLevel(),
    255
    )
    if (input.buttonIsPressed(Button.A)) {
        basic.showNumber(input.lightLevel())
    }
    if (input.lightLevel() < 50) {
        music.play(music.tonePlayable(784, music.beat(BeatFraction.Whole)), music.PlaybackMode.UntilDone)
    } else {
        music.stopAllSounds()
    }
})
```


## Descarga y prueba

Descarga el código en tu @boardname@ y ¡mide el nivel de luz a tu alrededor!
