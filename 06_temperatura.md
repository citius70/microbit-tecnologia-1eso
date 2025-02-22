# Actividad de temperatura

Mide la temperatura con la placa @boardname@

¡Bienvenido! Esta actividad te enseñará cómo medir la temperatura en el @boardname@. ¡Empecemos!


## {Paso 1}

Queremos mostrar la temperatura al agitar. Para hacer esto, necesitamos registrar el evento `si agitado` que se ejecutará cada vez que el usuario agite el @boardname@; En el navegador web, haga clic en el botón denominado "SHAKE" debajo del simulador para generar un evento de vibración.

```blocks
input.onGesture(Gesture.Shake, () => {
    })
```
## {Paso 2}

Midamos la temperatura y luego almacenemos en ella una variable `temp`. La temperatura se mide en **Celsius**, por lo que un valor de `29` equivale a 29 grados Celsius.

```blocks
input.onGesture(Gesture.Shake, () => {
    let temp = input.temperature()
})
```
## {Paso 3}

Muestra el valor de `temp` en la pantalla.

```blocks
input.onGesture(Gesture.Shake, () => {
    let temp = input.temperature()
    basic.showNumber(temp)
})
```

* haz clic en ejecutar para ver si el código funciona como se espera.



## {Paso 4}

Agreguemos el código para mostrar el texto **`Temperatura =  `**  con un bloque `mostrar cadena`. Modifique el bloque `mostrar cadena` para mostrar el texto lentamente en un intervalo de `300` milisegundos.

```blocks
input.onGesture(Gesture.Shake, () => {
    let temp = input.temperature()
    basic.showString("Temperatura = ")
    basic.showNumber(temp)
    })
```

* Ejecute el código para ver si funciona como se espera.

## Paso 5

Transfiere el código al @boardname@.