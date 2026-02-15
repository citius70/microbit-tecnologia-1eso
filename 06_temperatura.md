# Medidor de temperatura

## Objetivo @showdialog

¡Bienvenido! Esta actividad te enseñará cómo **medir la temperatura** en el @boardname@. ¡Empecemos! 🌡️

![Outdoor thermometer](/static/courses/ucp-science/temperature/heat-of-day.jpg)


## Medición de la temperatura al agitar

**Objetivo**: Mostrar la temperatura al agitar. 
**Instrucciones**:
1. Añadir el evento ``||input:si agitado||`` que se ejecutará cada vez que el usuario agite el @boardname@.

```blocks
input.onGesture(Gesture.Shake, () => {
    })
```
## Crear una variable

**Objetivo**: Debido a que el valor la temperatura va a **cambiar** de manera frecuente hay que ir guardando su valor en una **``variable``**.
**Instrucciones**:
1. En la categoría ``||Variables: Variables||``  haz click en ``||crea una variable||`` y ponle el nombre de ``temp``.



## Almacenar el valor de la temperatura en la variable

**Objetivo**: Ahora hagamos que el valor de la temperatura medido por el sensor de @boardname@ se **almacene (se fije) en la variable** ``temp``  
**Instrucciones**: Intenta completar este bloque ``||variables: fijar [temp] a (temperatura ºC)||``

    * La temperatura se mide en **Celsius**, por lo que un valor de `29` equivale a 29 grados Celsius.

```blocks
input.onGesture(Gesture.Shake, () => {
    let temp = input.temperature()
})
```
## Mostrar la temperatura

**Objetivo**: Hagamos que el valor de la variable ``temp`` se muestre en pantalla.
**Instrucciones**: Intenta completar este bloque ``||basic: mostrar número (temp)||``.
**Prueba**: Haz clic en el botón ``SHAKE`` para ver si el código funciona como se espera.

```blocks
input.onGesture(Gesture.Shake, () => {
    let temp = input.temperature()
    basic.showNumber(temp)
})
```

## Completar el texto

Agreguemos el código ``||basic: mostrar cadena||``  para mostrar el texto **`Temperatura =  `**  con un bloque `mostrar cadena`. Modifique el bloque `mostrar cadena` para mostrar el texto lentamente en un intervalo de `300` milisegundos.

```blocks
input.onGesture(Gesture.Shake, () => {
    let temp = input.temperature()
    basic.showString("Temperatura = ")
    basic.showNumber(temp)
    })
```

* Ejecuta el código para ver si funciona como se espera.

## Transferir el programa

Transfiere el código al @boardname@ y comprueba el funcionamiento.
