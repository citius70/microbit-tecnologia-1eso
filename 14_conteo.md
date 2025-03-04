# Recuento de hombres/mujeres

## Objetivo

El propósito de esta actividad es hacer un recuento del número de **hombres y de mujeres** que cruzan nuestro instituto hacia el centro de Pontevedra.

## Configuración

La programación de este proyecto implicará varios pasos:

1. El bloque ``||basic:al iniciar|||``:

    * mostrará el título del proyecto.
    * también declarará las variables que se utilizarán en el proyecto.
    
2. Los botones ``||input:al presionar el botón [A]||`` y ``||input:al presionar el botón [B]||``:
    
    * están programados para sumar 1 al contador del rasgo asociado a ese botón. A para el hombre y B para la mujer.

3. El bloque  ``||input:al presionar el botón A+B||`` está programado para:

    * mostrar el nombre del primer rasgo y el recuento.
    * a continuación, el nombre del segundo rasgo y su recuento,
    * finalmente, se mostrará el número total contado en ambos botones. 

4. El evento ``||input: al [mantener pulsado] el logotipo ||`` puede ser programado para borrar los datos y empezar de nuevo.


## Paso 1: bloque ``||basic:al iniciar|||``

1. El evento ``||basic:al iniciar||`` mostrará el título en mayúsculas: ``CONTADOR DE PERSONAS``.

    * El texto se pone en el bloque ``||basic:mostrar cadena|||`` en mayúsculas porque es más fácil de leer cuando se muestra en la pantalla LED.

2. Desde la caja de herramientas ``||variables:Variables||`` crea variables llamadas ``hombres``, ``mujeres``, y ``total``. 

    * Estas se utilizarán como contadores para llevar la cuenta de los rasgos contados.
 
```blocks
let hombres = 0
let mujeres = 0
let total = 0
basic.showString("CONTADOR DE PERSONAS")
```

Las variables se declaran en el evento ``||basic:al iniciar||`` y se les asigna un valor inicial de `0`.

## Paso 2: bloque  ``||input: al presionar el botón [A]||``

1. El bloque ``||input:al presionar el botón A||`` se utilizará para contar el primer rasgo (HOMBRE) añadiendo `1` a la variable ``hombres`` cada vez que se pulse el botón.

2. El bloque ``||variables:cambiar [hombre] por 1||`` se utiliza para incrementar el número de ``hombres`` en 1.

    * Esto se puede intrepretar como: ``a la variable hombres, súmale 1``.

3. La siguiente línea ``||basic: mostrar número (hombres)||`` se utiliza para mostrar el valor actual de ``hombres``.
 
```blocks
let hombres = 0

input.onButtonPressed(Button.A, () => {
    hombres += 1
    basic.showNumber(hombres)
})
```

## Paso 3: bloque  ``||input: al presionar el botón [B]||``

1. El código para ``||input:al presionar el botón B||`` es el mismo que el de ``||input:al presionar el botón A||`` excepto que se usa para mantener la cuenta de ``mujeres``.
 
```blocks
let mujeres = 0

input.onButtonPressed(Button.B, () => {
    mujeres += 1
    basic.showNumber(mujeres)
})
```

## Paso 4: bloque  ``||input: al presionar el botón [A+B]||``

1. El bloque ``||input:al presionar el botón [A B]||`` se utiliza para mostrar el nombre y el recuento de cada rasgo y el total de observaciones realizadas mostrando la información en la pantalla LED.
2. Tras el cálculo aparece el nombre ``H: `` seguido de su valor. (H de hombres)
3. Lo mismo se hace para ``M: ``. (M de mujeres)
4. Las 2 últimas líneas muestran la etiqueta ``T: ``  y su valor calculado. (T de total)
 
```blocks
let hombres = 0
let mujeres = 0
let total = 0

input.onButtonPressed(Button.AB, () => {
    total += hombres + mujeres
    basic.showString("H: ")
    basic.showNumber(hombres)
    basic.showString("M: ")
    basic.showNumber(mujeres)
    basic.showString("T: ")
    basic.showNumber(total)
})
```

## Paso 5: bloque  ``||input: al [mantener pulsado] el logotipo ||``

1. El evento ``||input: al [mantener pulsado] el logotipo ||``` se utiliza para borrar el valor de todas las variables.
2. Esto se hace volviendo a poner los valores de cada una de las variables a `0`. 

¡Atención!: Este procedimiento borra todos los datos del @boardname@.

 
```blocks
let hombres = 0
let mujeres = 0
let total = 0
input.onLogoEvent(TouchButtonEvent.LongPressed, function () {
    hombres = 0
    mujeres = 0
    total = 0
})
```

## Paso 5: Programa mejorado

En la ayuda puedes observar un programa más completo que mejorará su funcionamiento.

```blocks
input.onButtonPressed(Button.A, function () {
    hombres += 1
    basic.showLeds(`
        . . . . .
        . . . . .
        # . . . .
        . . . . .
        . . . . .
        `)
    basic.showNumber(hombres)
    basic.pause(1000)
    basic.clearScreen()
})
input.onLogoEvent(TouchButtonEvent.LongPressed, function () {
    basic.showIcon(IconNames.Skull)
    hombres = 0
    mujeres = 0
    total = 0
    basic.showLeds(`
        . . . . .
        . . . . .
        # . . . #
        . . . . .
        . . . . .
        `)
})
input.onButtonPressed(Button.AB, function () {
    basic.clearScreen()
    total += hombres + mujeres
    basic.showString("T:")
    basic.showNumber(total)
    basic.pause(1000)
    basic.clearScreen()
    basic.showString("H:")
    basic.showNumber(hombres)
    basic.pause(1000)
    basic.clearScreen()
    basic.showString("M:")
    basic.showNumber(mujeres)
    basic.pause(1000)
    total = 0
    basic.showLeds(`
        . . . . .
        . . . . .
        # . . . #
        . . . . .
        . . . . .
        `)
})
input.onButtonPressed(Button.B, function () {
    mujeres += 1
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . #
        . . . . .
        . . . . .
        `)
    basic.showNumber(mujeres)
    basic.pause(1000)
    basic.clearScreen()
})
let total = 0
let mujeres = 0
let hombres = 0
hombres = 0
mujeres = 0
total = 0
basic.showLeds(`
    . . . . .
    . . . . .
    # . . . #
    . . . . .
    . . . . .
    `)
```

```sim
input.onButtonPressed(Button.A, function () {
    hombres += 1
    basic.showLeds(`
        . . . . .
        . . . . .
        # . . . .
        . . . . .
        . . . . .
        `)
    basic.showNumber(hombres)
    basic.pause(1000)
    basic.clearScreen()
})
input.onLogoEvent(TouchButtonEvent.LongPressed, function () {
    basic.showIcon(IconNames.Skull)
    hombres = 0
    mujeres = 0
    total = 0
    basic.showLeds(`
        . . . . .
        . . . . .
        # . . . #
        . . . . .
        . . . . .
        `)
})
input.onButtonPressed(Button.AB, function () {
    basic.clearScreen()
    total += hombres + mujeres
    basic.showString("T:")
    basic.showNumber(total)
    basic.pause(1000)
    basic.clearScreen()
    basic.showString("H:")
    basic.showNumber(hombres)
    basic.pause(1000)
    basic.clearScreen()
    basic.showString("M:")
    basic.showNumber(mujeres)
    basic.pause(1000)
    total = 0
    basic.showLeds(`
        . . . . .
        . . . . .
        # . . . #
        . . . . .
        . . . . .
        `)
})
input.onButtonPressed(Button.B, function () {
    mujeres += 1
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . #
        . . . . .
        . . . . .
        `)
    basic.showNumber(mujeres)
    basic.pause(1000)
    basic.clearScreen()
})
let total = 0
let mujeres = 0
let hombres = 0
hombres = 0
mujeres = 0
total = 0
basic.showLeds(`
    . . . . .
    . . . . .
    # . . . #
    . . . . .
    . . . . .
    `)
```