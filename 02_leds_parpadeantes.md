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

Comencemos añadiendo una línea de cófigo que enciende el LED en la posición (0, 0) ``||led.plot(0,0)||``.

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

¡Atención!. El actual código funciona, pero hace que el LED parpadea una sola vez.

Para solucionarlo, vamos a utilizar el bucle `por siempre` y mover el código dentro de él para que se repita una y otra vez. Puedes eliminar el bloque `plot` ya que no es necesario ahora.

```blocks
basic.forever(() => {
    led.plot(0, 0)
    basic.pause(500)
    led.unplot(0, 0)
    basic.pause(500)
})
```

## ~avatar boothing

Muy bien, estás preparado para continuar con algún desafío.ns/blink/challenges)!

## ~

## Desafío 1

Mostremos una "cara sonriente". Comenzaremos con los ojos en este desafío y lo completaremos en el Desafío 2.

Añade `graficar(1,1)` y `graficar(3,1)` y debajo `graficar(2,2)` ; después añade `ocultar(1,1)`, `ocultar(3,1)` y `ocultar(2,2)` después `pausa`.

Cuando esté preparado, no olvides probar el código.

```blocks
basic.forever(() => {
    led.plot(2, 2)
    led.plot(1, 1)
    led.plot(3, 1)
    basic.pause(500)
    led.unplot(2, 2)
    led.unplot(1, 1)
    led.unplot(3, 1)
    basic.pause(500)
})
```

## Desafío 2

Completa el código para conseguir una "cara sonriente".

```sim
basic.forever(() => {
    led.plot(1, 1)
    led.plot(3, 1)
    led.plot(2, 2)
    led.plot(0, 3)
    led.plot(4, 3)
    led.plot(1, 4)
    led.plot(2, 4)
    led.plot(3, 4)
    basic.pause(500)
    led.unplot(1, 1)
    led.unplot(3, 1)
    led.unplot(2, 2)
    led.unplot(0, 3)
    led.unplot(4, 3)
    led.unplot(1, 4)
    led.unplot(2, 4)
    led.unplot(3, 4)
    basic.pause(500)
})
```


