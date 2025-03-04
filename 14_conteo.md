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

2. El bloque  ``||input:al presionar el botón A+B||`` está programado para:

    * mostrar el nombre del primer rasgo y el recuento.
    * a continuación, el nombre del segundo rasgo y su recuento,
    * finalmente, se mostrará el número total contado en ambos botones. 

3. El evento ``||input:al agitar|||`` puede ser programado para borrar los datos y empezar de nuevo.


### Paso 1: en el evento; Al iniciar

1. Nombra el proyecto, «Contador de personas».
2. El evento ``||basic:on start||`` mostrará el título y propósito del microbit en mayúsculas, «CONTADOR DE PERSONAS». El texto se pone en el bloque ``||basic:show string|||`` (el título se pone en el evento ``||basic:on start|||`` para que cuando se inicie el microbit muestre para qué está programado. Se hace en mayúsculas porque es más fácil de leer cuando se muestra en la pantalla LED).
3. Desde la caja de herramientas ``||variables:Variables||`` cree variables llamadas ``hombre``, ``mujer``, y ``total``. Éstas se utilizarán como contadores para llevar la cuenta de los rasgos contados. Las variables se nombran para describir lo que van a almacenar. Las variables se nombran normalmente usando letras minúsculas y/o dígitos. Si se trata de un nombre de 2 palabras, por lo general se nombran usando camelCaps (sin espacios, pero con una mayúscula donde comienza la segunda palabra. Por ejemplo ``totalCount``, ``randNumber``, etc.)
 
```blocks
let hombres = 0
let mujeres = 0
let total = 0
basic.showString("CONTADOR DE PERSONAS")
```

Las variables se declaran en el evento ``||basic:al iniciar||`` y se les asigna un valor inicial de `0`.

### en el evento: ``al presionar el botón [A]``

1. El evento ``||input:al presionar el botón A||`` se utilizará para contar el primer rasgo (HOMBRE) añadiendo `1` a la variable ``hombres`` cada vez que se pulse el botón.
2. El evento ``||variables:cambiar hombre por 1||`` se utiliza para incrementar el número de hombres en 1. Esto se puede intrepretar como: "a la variable ``hombres``, súmale 1".
3. La siguiente línea se utiliza para mostrar el valor actual de ``hombres``.
 
```blocks
let hombres = 0


input.onButtonPressed(Button.A, () => {
    hombres += 1
    basic.showNumber(hombres)
})
```

### en el evento: ``al presionar el botón [B]``

1. El código para ``||input:al presionar el botón B||`` es el mismo que el de ``||input:al presionar el botón A||`` excepto que se usa para mantener una cuenta en ``mujeres``.
 
```blocks
let mujeres = 0

input.onButtonPressed(Button.B, () => {
    mujeres += 1
    basic.showNumber(mujeres)
})
```

### en el evento:  ``al presionar el botón [A+B]``

1. El evento ``||input:al presionar el botón A+B||`` se utiliza para mostrar el nombre y el recuento de cada rasgo y el total de observaciones realizadas mostrando la información en la pantalla LED.
2. Tras el cálculo aparece el nombre ``hombres`` seguido de su valor.
3. Lo mismo se hace para ``mujeres``.
4. Las 2 últimas líneas muestran la etiqueta `«TOTAL»` y su valor calculado. 
 
```blocks
let hombres = 0
let mujeres = 0
let total = 0

input.onButtonPressed(Button.AB, () => {
    total += hombres + mujeres
    basic.showString("H:")
    basic.showNumber(hombres)
    basic.showString("M:")
    basic.showNumber(mujeres)
    basic.showString("TOTAL")
    basic.showNumber(total)
})
```

### en el evento: ``si agitado``

1. El evento ``||basic:al agitar||`` se utiliza para borrar el valor de todas las variables.
2. Esto se hace volviendo a poner los valores de cada una de las variables a `0`. 
 
```blocks
let hombres = 0
let mujeres = 0
let total = 0
input.onGesture(Gesture.Shake, () => {
    hombres = 0
    mujeres = 0
    total = 0
})
```


### ~hint

#### Atención

Este procedimiento borra todos los datos del @boardname@.
