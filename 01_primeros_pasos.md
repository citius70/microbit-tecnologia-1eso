# Primeros pasos con @boardname@



## Paso 1

Bienvenid@s!

Sitúa el bloque ``||basic:mostar cadena:"Hola"||`` en el espacio ``||basic:al iniciar||``. Reemplaza el texto **``"Hola"``** con tu **nombre**. ¿Viste cómo se desplaza el texto?

```blocks
basic.showString("Alberto")
```

## Paso 2

El texto dejó de desplazarse. Arrastra el bloque ``||input:al presionar el botón: A||`` y coloca ``||basic:mostrar cadena:(TU_NOMBRE)||`` en su ranura. Ahora pulsa el botón **`A`** y mira como se desplaza el texto.

```blocks
input.onButtonPressed(Button.A, () => {
    basic.showString(«¡Alberto»)
});
```

## Paso 3

Coloca algunos bloques para mostrar un **``smiley``** cuando se pulse el botón **`B`**. 

Para ello, arrastra el bloque ``||basic:mostrar LEDs||`` dentro de otro bloque ``||input:al presionar el botón: B||`` (Usa el desplegable para encontrar **`B`**).

```blocks
input.onButtonPressed(Button.B, () => {
    basic.showLeds(`
    . . . . .
    . # . # .
    . . . . .
    # . . . #
    . # # # .
    `)
})
```

## Paso 4

Ahora, haz que se muestre un **número al azar** al *agitar** el @boardname@.

Coloca los bloques ``||basic:mostrar número|||`` y ``||math:escoger al azar||`` en un bloque ``||input:si agitado||`` para construir un dado.

```blocks
input.onGesture(Gesture.Shake, () => {
    basic.showNumber(randint(0, 10))
})
```

## Paso 5

Un dado típico muestra valores de `1` a `6`. Así que, en  ``||math:escoger al azar||``, ¡no olvides elegir bien los valores mínimo 1 y máximo 6!

```blocks
input.onGesture(Gesture.Shake, () => {
    basic.showNumber(randint(1, 6))
})
```

## Paso 6

Ahora vamos a **transferir el programa** a la tarjeta controladora @boardname@.

Conecta la tarjeta al ordenador con un cable USB y haz clic en ``|Descargar|``. Guarda el programa en la unidad **@drivename@**. Esto transfiere tu código al @boardname@.

## Paso 7

En el @boardname@, pulse el botón **`A`** para desplazar el texto. Pulse el botón **`B`** para mostrar un `smile`. Agite el @boardname@ y mira qué número ha elegido.

## Paso 8

¡Bien hecho! Ha completado su primera actividad Microsoft MakeCode.😛