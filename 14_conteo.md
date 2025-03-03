# Conteo

## Configuración

1. La codificación de este proyecto implicará varios pasos. 
2. El bloque ``||basic:al iniciar|||`` mostrará el título del proyecto. También declarará las variables que se utilizarán en el proyecto. Los botones **A** y **B** están programados para sumar 1 a la cuenta del rasgo asociado a ese botón. 
3. Los botones **A** y **B** están programados para mostrar el nombre del primer rasgo y el recuento. A continuación, el nombre del segundo rasgo y su recuento. Finalmente se mostrará el número total contado en ambos botones. 
4. El evento ``||input:al agitar|||`` puede ser programado para borrar los datos y empezar de nuevo.

### ~ hint

#### Ejemplo de experimento de rasgos de población

Vea este vídeo sobre cómo realizar un experimento de rasgos poblacionales.

https://youtu.be/NNZEMiJHY2o

### ~

## Code

### Entorno de programación MakeCode

1. Abre el editor MakeCode micro:bit en un navegador en: @homeurl@.

### en el evento; Al iniciar

1. Nombra el proyecto, «Contador de rasgos de población».
2. El evento ``||basic:on start||`` mostrará el título y propósito del microbit en mayúsculas, «POPULATION TRAIT COUNTER». El texto se pone en el bloque ``||basic:show string|||`` (el título se pone en el evento ``||basic:on start|||`` para que cuando se inicie el microbit muestre para qué está programado. Se hace en mayúsculas porque es más fácil de leer cuando se muestra en la pantalla LED).
3. Desde la caja de herramientas ``||variables:Variables||`` cree variables llamadas ``trait1``, ``trait2``, y ``total``. Éstas se utilizarán como contadores para llevar la cuenta de los rasgos contados. Las variables se nombran para describir lo que van a almacenar. Las variables se nombran normalmente usando letras minúsculas y/o dígitos. Si se trata de un nombre de 2 palabras, por lo general se nombran usando camelCaps (sin espacios, pero con una mayúscula donde comienza la segunda palabra. Por ejemplo ``totalCount``, ``randNumber``, etc.)
 
```blocks
let rasgo1 = 0
let rasgo2 = 0
let total = 0
basic.showString("CONTADOR DE CARACTERES DE POBLACIÓN")
```

Las variables se declaran en el evento ``||basic:al iniciar||`` y se les asigna un valor inicial de `0`.

### en el evento: Botón «A» Pulsado

1. El evento ``||input:al presionar el botón A||`` se utilizará para contar el primer rasgo añadiendo `1` a ``rasgo1`` cada vez que se pulse el botón.
2. El evento ``||variables:cambiar rasgo1 por 1||`` se utiliza para incrementar el número. Esto se puede intrepretar como: "a la varaiable rasgo1, súmale 1".
3. La siguiente línea se utiliza para mostrar el valor actual de ``rasgo1``.
 
```blocks
let rasgo1 = 0


input.onButtonPressed(Button.A, () => {
    rasgo1 += 1
    basic.showNumber(rasgo1)
})
```

### en el evento: Botón «B» Pulsado

1. El código para ``||input:al presionar el botón B||`` es el mismo que el de ``||input:al presionar el botón A||`` excepto que se usa para mantener una cuenta en ``rasgo2``.
 
```blocks
let rasgo2 = 0

input.onButtonPressed(Button.B, () => {
    rasgo2 += 1
    basic.showNumber(rasgo2)
})
```

### en el evento:  Botón «A+B» Pulsado

1. El evento ``||input:al presionar el botón A+B||`` se utiliza para mostrar el nombre y el recuento de cada rasgo y el total de observaciones realizadas mostrando la información en la pantalla LED.
2. Tras el cálculo aparece el nombre rasgo1 seguido de su valor.
3. Lo mismo se hace para rasgo2.
4. Las 2 últimas líneas muestran la etiqueta `«TOTAL»` y su valor calculado. 
 
```blocks
let rasgo1 = 0
let rasgo2 = 0
let total = 0

input.onButtonPressed(Button.AB, () => {
    total += rasgo1 + rasgo2
    basic.showString(«RASGO 1»)
    basic.showNumber(rasgo1)
    basic.showString(« RASGO 2»)
    basic.showNumber(rasgo2)
    basic.showString(« TOTAL»)
    basic.showNumber(total)
})
```

### en el evento Shake

1. El evento ``||basic:al agitar||`` se utiliza para borrar el valor de todas las variables.
2. Esto se hace volviendo a poner los valores de cada una de las variables a `0`. 
 
```blocks
let rasgo1 = 0
let rasgo2 = 0
let total = 0
input.onGesture(Gesture.Shake, () => {
    rasgo1 = 0
    rasgo2 = 0
    total = 0
})
```


### ~hint

#### Warning

This procedure could be problematic if the @boardname@ is shaken to much while it is used in counting.

### ~

## Extensions

This project could easily be modified to keep track of scores for 2 different teams. What other ideas can you think of that counters could be used for?

## ~button /courses/ucp-science/population/resources
NEXT: Resources
## ~

<br/>
Adapted from "[Population Trait Data Counter](https://drive.google.com/open?id=1CC5uhIoZK4Q67vU5Ldwna6GEeZYXNDYzgO8BUUjPuwI)" by [C Lyman](http://utahcoding.org) [![CC BY-NC-SA](https://licensebuttons.net/l/by-nc-sa/4.0/80x15.png)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

