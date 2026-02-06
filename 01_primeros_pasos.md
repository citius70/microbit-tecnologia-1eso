# Primeros pasos con @boardname@

## Objetivo @showdialog

En esta actividad veremos algunas **funciones básicas** que puede realizar @boardname@.

Aprenderás a utilizar los botones `|A|` y `|B|`, la pantalla LEDs, gestos, enviar el programa al micro:bit...

![Heart shape in the LEDs](/static/mb/projects/flashing-heart/sim.gif)

## Mostrar texto en la pantalla de LEDS

* **Objetivo**: Vamos a convertir a @boardname @ en tu tarjeta de identificación.

**Instrucciones**: Arrastra el bloque ``||basic:mostar cadena:"Hola"||`` (debajo de la **caja de herramientas**) dentro de ``||basic:al iniciar||``.

Reemplaza el texto **``"Hola"``** con tu **nombre**. ¿Viste cómo se desplaza el texto?

```blocks
basic.showString("Alberto")
```


## Botón |A|


El texto dejó de desplazarse. Vamos a intentar que tu nombre aparezca cuando pulsas el **botón `|A|`**:

Arrastra el bloque ``||input:al presionar el botón: A||`` y coloca ``||basic:mostrar cadena:("TU_NOMBRE")||`` en su ranura. Ahora pulsa el botón **`A`** y mira como se desplaza el texto.

```blocks
input.onButtonPressed(Button.A, () => {
    basic.showString(«¡Alberto»)
});
```

## Botón |B|

* **Objetivo**: Coloca algunos bloques para mostrar un **``smiley``** (CARA SONRIENTE) cuando se pulse el botón **`B`**. 

**Instrucciones**: Arrastra el bloque ``||basic:mostrar LEDs||`` dentro de otro bloque ``||input:al presionar el botón: B||`` (Usa el desplegable para encontrar **`B`**).
Dibuja una cara sonriente en la pantalla de 25 (5x5) LEDs.

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

## Gestos (agitar)

* **Objetivo**: Ahora, haz que se muestre un **número al azar** al *agitar* 🪇  el @boardname@.

**Instrucciones**: Coloca los bloques ``||basic:mostrar número|||`` y ``||math:escoger al azar||`` en un bloque ``||input:si agitado||`` para construir un dado.
Agita la tarjeta una vez para que se muestre un número al azar. Repítelo varias veces.

```blocks
input.onGesture(Gesture.Shake, () => {
    basic.showNumber(randint(0, 10))
})
```

## Programar un dado electrónico

* **Objetivo**: Convierte @boardname@ en un dado típico 🎲 que muestre valores de `1` a `6`.

**Instrucciones**: En  ``||math:escoger al azar de (1) a (6)||``, ¡no olvides elegir bien los valores mínimo 1 y máximo 6!

```blocks
input.onGesture(Gesture.Shake, () => {
    basic.showNumber(randint(1, 6))
})
```

## Enviar el programa a micro:bit

Ahora vamos a **transferir el programa** a la tarjeta controladora @boardname@.

Conecta la tarjeta al ordenador con un cable USB y haz clic en ``|Descargar|``. Guarda el programa en la unidad **@drivename@**. Esto transfiere tu código al @boardname@.


En el @boardname@, pulse el botón **`A`** para desplazar el texto. Pulse el botón **`B`** para mostrar un `smile`. Agita el @boardname@ y mira qué número ha elegido.

## Final

¡Bien hecho! Has completado tu primera actividad. 😛
