# LEDs parpadeantes

Enciende y apaga un LED constantemente

## ~avatar avatar

```sim
basic.forever(() => {
    led.plot(0, 0)
    basic.pause(500)
    led.unplot(0, 0)
    basic.pause(500)
})
```
Constuyamos un LED parpadeante!

## ~

El concepto es muy simple: enciende el LED, espera un rato, apaga el LED, espera de nuevo y se repite de nuevo.

Comencemos añadiendo una línea de cófigo que enciende el LED en la posición (0, 0).

```blocks
led.plot(0, 0)
```

Prueba el programa en el simulador para asegurarte de su funcionamiento.

Ahora, añadamos código para `pausar` 0.5 segundos (500 milisegundos) y apagar el LED.

```blocks
led.plot(0, 0)
basic.pause(500)
led.unplot(0,0)
```

Hemos encendido y apagado el LED una sola vez. Añadamos otra pausa y encendamos el LED otra vez.

```blocks
led.plot(0, 0)
basic.pause(500)
led.unplot(0, 0)
basic.pause(500)
led.plot(0, 0)
```

¡Atención!. El actual cófigo funciona, pero hace que el LED parpadea una sola vez.

Para solucionarlo, vamos a utilizar el bucle `por siempre` y mover el código dentro de él para que se repita una y otra vez. Puedes eliminar el bloque -------  ya que no es necesario ahora.

```blocks
basic.forever(() => {
    led.plot(0, 0)
    basic.pause(500)
    led.unplot(0, 0)
    basic.pause(500)
})
```

## ~avatar boothing

Excellent, you're ready to continue with the [challenges](/lessons/blink/challenges)!

## ~