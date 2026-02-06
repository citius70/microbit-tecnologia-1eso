# Primeros pasos con @boardname@

## Objetivo @showdialog

En esta actividad veremos algunas **funciones básicas** que puede realizar @boardname@.

Aprenderás a utilizar los botones `A` y `B`, la pantalla LEDs, gestos, enviar el programa al micro:bit...

![Heart shape in the LEDs](/static/mb/projects/flashing-heart/sim.gif)

## Paso 1: Mostrar texto en la pantalla de LEDS

Arrastra el bloque ``||basic:mostar cadena:"Hola"||`` dentro de ``||basic:al iniciar||``.

Reemplaza el texto **``"Hola"``** con tu **nombre**. ¿Viste cómo se desplaza el texto?



```blocks
basic.showString("Alberto")
```


```sim
basic.showString("Asimlberto")
```
## Paso 2: Botón A

El texto dejó de desplazarse. Vamos a intentar que tu nombre aparezca cuando pulsas el **botón A**:

* Arrastra el bloque ``||input:al presionar el botón: A||`` y coloca ``||basic:mostrar cadena:("TU_NOMBRE")||`` en su ranura. Ahora pulsa el botón **`A`** y mira como se desplaza el texto.

```blocks
input.onButtonPressed(Button.A, () => {
    basic.showString(«¡Alberto»)
});
```

## Paso 3: Botón B

Coloca algunos bloques para mostrar un **``smiley``** cuando se pulse el botón **`B`**. 

* Para ello, arrastra el bloque ``||basic:mostrar LEDs||`` dentro de otro bloque ``||input:al presionar el botón: B||`` (Usa el desplegable para encontrar **`B`**).

    * Dibuja una cara sonriente emn la pantalla de 25 (5x5) LEDs.

```blocks
input.onButtonPressed(Button.B, () => {
    basic.showLeds(`
    # # . # #
    . # . # .
    . . # . .
    # . . . #
    . # # # .
    `)
})
```

## Paso 4: Gestos (agitar)

Ahora, haz que se muestre un **número al azar** al *agitar* 🪇  el @boardname@.

* Coloca los bloques ``||basic:mostrar número|||`` y ``||math:escoger al azar||`` en un bloque ``||input:si agitado||`` para construir un dado.

```blocks
input.onGesture(Gesture.Shake, () => {
    basic.showNumber(randint(0, 10))
})
```

## Paso 5: Programar un dado electrónico

Un dado típico 🎲 muestra valores de `1` a `6`. Así que, en  ``||math:escoger al azar de (1) a (6)||``, ¡no olvides elegir bien los valores mínimo 1 y máximo 6!

```blocks
input.onGesture(Gesture.Shake, () => {
    basic.showNumber(randint(1, 6))
})
```

## Paso 6: Enviar el programa a micro:bit

Ahora vamos a **transferir el programa** a la tarjeta controladora @boardname@.

Conecta la tarjeta al ordenador con un cable USB y haz clic en ``|Descargar|``. Guarda el programa en la unidad **@drivename@**. Esto transfiere tu código al @boardname@.


En el @boardname@, pulse el botón **`A`** para desplazar el texto. Pulse el botón **`B`** para mostrar un `smile`. Agita el @boardname@ y mira qué número ha elegido.

## Final

¡Bien hecho! Ha completado su primera actividad Microsoft MakeCode.😛
