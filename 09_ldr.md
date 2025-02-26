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

## Paso 2: Traza el nivel de luz

Ahora, vamos a ``||led:trazar un gráfico de barras||`` que muestre el de las ``|variables:luzActual||`` para el ``||input:nivel de luz||``. Establece el límite en 255.

```blocks
let lectura = 0
basic.forever(function() {
    reading = input.lightLevel()
    led.plotBarGraph(lectura, 255)
})
```

## Paso 2: Visualiza el nivel de luz

Ve al simulador y observa como cambia el gráfico de barras mientras ajustas el control del nivel de luz.

## Paso 3: Mostrar la lectura como número

Añade el código a ``||basic:show a number||`` para el valor de ``||variables:reading||``
``|logic:if||`` se pulsa el ``||input:botón A||``.

Bloques
let lectura = 0
basic.forever(function() {
    lectura = input.lightLevel()
    led.plotBarGraph(lectura, 255)
    if (input.buttonIsPressed(Button.A)) {
        basic.showNumber(lectura)
    }
})
```

## Descarga y prueba

Descarga el código en tu @nombredelaplataforma@ y ¡mide el nivel de luz a tu alrededor!

Traducción realizada con la versión gratuita del traductor DeepL.com