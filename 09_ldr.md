# Medidor de Nivel de Luz

## Introducción @unplugged

Este programa crea un medidor de nivel de luz. Utiliza el sensor de luz del @boardname@ para detectar la cantidad de luz.

## Paso 1: Guardar una lectura

Crea una variable, ``||variables:luzActual||`` en la que vamos a guardar (fijar) el ``||input:nivel luz||`` que te rodea. Haz esto dentro de un bucle ``||basic:para siempre||``.

```blocks
let luzActual = 0
basic.forever(function() {
    luzActual = input.lightLevel()
})
```

## Paso 2: Trazar el nivel de luz

Ahora, vamos a ``||led:trazar un gráfico de barras||`` que muestre el nivel de ``|variables:luzActual||`` para el ``||input:nivel de luz||``. Establece el límite en 255.

```blocks
let luzActual = 0
basic.forever(function() {
    luzActual = input.lightLevel()
    led.plotBarGraph(luzActual, 255)
})
```

## Paso 3: Visualiza el nivel de luz

Ve al simulador y observa como cambia el gráfico de barras mientras ajustas el control del nivel de luz.

## Paso 4: Mostrar la lectura como número

Añade el código a ``||basic:enseñar un número||`` para el valor de ``||variables:luzActual||``
``|logic:si||`` se pulsa el ``||input:botón A||``.

```blocks
let luzActual = 0
basic.forever(function() {
    luzActual = input.lightLevel()
    led.plotBarGraph(lectura, 255)
    if (input.buttonIsPressed(Button.A)) {
        basic.showNumber(luzActual)
    }
})
```

## Descarga y prueba

Descarga el código en tu @nombredelaplataforma@ y ¡mide el nivel de luz a tu alrededor!

Traducción realizada con la versión gratuita del traductor DeepL.com