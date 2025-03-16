# Medidor de nivel de sonido

## Introducción @unplugged

Este programa utiliza el **micrófono** del @boardname@ para:

* visualizar gráficamente el **nivel de sonido** ambiental.



## Paso 1: Trazar el nivel de sonido en una gráfica

Dentro del bloque ``||basic:para siempre||`` vamos a  ``||led: trazar un gráfico de barras||`` que muestre el nivel de  ``||input:nivel de sonido||``. 

El micrófono del @boardname@ nos devuelve el valor:

* 0 (mínimo) cuando se encuentra en total silencio,

* 255 (máximo) cuando el ruido es máximo.

Por ello, establece el límite de la gráfica en 255 para que coincida con el valor máximo medido por el sensor.

```blocks
basic.forever(function () {
    led.plotBarGraph(
    input.soundLevel(),
    255
    )
    }
})
```

Mira el simulador y observa como cambia el gráfico de barras con el nivel de ruido.
