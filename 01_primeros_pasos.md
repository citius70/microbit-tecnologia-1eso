# Primeros pasos con @boardname@

## Paso 1

Bienvenid@s!

Sitúa el bloque ``||basic:mostar cadena||`` en el espacio ``||basic:al iniciar||``. Reemplaza el texto ``"Hola"`` con tu nombre. Viste cómo se desplaza el texto?

```blocks
basic.showString("Alberto")
```

## Paso 2

El texto dejó de desplazarse. Coloca el bloque ``||basic:mostrar cadena||`` en la ranura ``||input:al presionar el botón||`` para desplazar su nombre cuando se pulse el botón **A**.

```blocks
input.onButtonPressed(Button.A, () => {
    basic.showString(«¡Alberto»)
});
```

## Paso 3

Coloca algunos bloques para mostrar un ``smiley`` cuando se pulse el botón **B**.

Usa el desplegable para encontrar ``B``.

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

Coloca los bloques ``||basic:mostrar número|||`` y ``|Math:escoger al azar||`` en un bloque ``||input:si agitado||`` para construir un dado.

```blocks
input.onGesture(Gesture.Shake, () => {
    basic.showNumber(randint(0, 10))
})
```

## Paso 5

Un dado típico muestra valores de `1` a `6`. Así que, en ``||Math:escoger al azar||``, ¡no olvides elegir bien los valores mínimo y máximo!

```blocks
input.onGesture(Gesture.Shake, () => {
    basic.showNumber(randint(1, 6))
})
```

## Paso 6
Si tienes un @boardname@, conéctale un cable USB y haz clic en ``|Descargar|``. Guarda el programa en la unidad **@drivename@**. Esto transfiere tu código al @boardname@.

## Paso 7

En el @boardname@, pulse el botón **A** para desplazar el texto. Pulse el botón **B** para mostrar un smiley. Agite el @boardname@ y vea qué número ha elegido.

## Paso 8

¡Bien hecho! Ha completado su primera actividad Microsoft MakeCode.😛