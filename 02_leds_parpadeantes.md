# LEDs parpadeantes

Enciende y apaga un LED constantemente

```sim
basic.forever(() => {
    led.plot(0, 0)
    basic.pause(1000)
    led.unplot(0, 0)
    basic.pause(1000)
})
```
Constuyamos un LED parpadeante!

## Paso 1

El concepto es muy simple: enciende el LED, espera un rato, apaga el LED, espera de nuevo y se repite de nuevo.

Comencemos añadiendo una línea de código que enciende el LED en la posición (0, 0) ``||led.graficar x=0, y=0||``.

```blocks
led.plot(0, 0)
```

Prueba el programa en el simulador para asegurarte de su funcionamiento.

## Paso 2
Ahora, añadamos código para `pausar` 1 segundo (1000 milisegundos) y apagar el LED. ``||basic.pausa ms(1000)||``.

```blocks
led.plot(0, 0)
basic.pause(1000)
led.unplot(0,0)
```
## Paso 3
Hemos encendido y apagado el LED una sola vez. Añadamos otra pausa y encendamos el LED otra vez.

```blocks
led.plot(0, 0)
basic.pause(1000)
led.unplot(0, 0)
basic.pause(1000)
led.plot(0, 0)
```

¡Atención!. El actual código funciona, pero hace que el LED parpadea una sola vez.

## Paso 4

Para solucionarlo, vamos a utilizar el bucle `por siempre` y mover el código dentro de él para que se repita una y otra vez. Puedes eliminar el bloque `plot` ya que no es necesario ahora.

```blocks
basic.forever(() => {
    led.plot(0, 0)
    basic.pause(1000)
    led.unplot(0, 0)
    basic.pause(1000)
})
```

## ~avatar boothing

Muy bien, estás preparado para continuar con algún desafío.

## ~

## Desafío 1

Mostremos una "cara sonriente". Comenzaremos con los ojos en este desafío y lo completaremos en el Desafío 2.

Añade ``||led.graficar(1,1)||`` y ``||led.graficar(3,1)||`` y debajo ``||led.graficar(2,2)||``. después añade ``||led.ocultar(1,1)||``, ``||led.ocultar(3,1)||`` y ``||plot.ocultar(2,2)||`` después ``||led.pausa ms (1000)||``.

Cuando esté preparado, no olvides probar el código.

```blocks
basic.forever(() => {
    led.plot(2, 2)
    led.plot(1, 1)
    led.plot(3, 1)
    basic.pause(1000)
    led.unplot(2, 2)
    led.unplot(1, 1)
    led.unplot(3, 1)
    basic.pause(1000)
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
    basic.pause(1000)
    led.unplot(1, 1)
    led.unplot(3, 1)
    led.unplot(2, 2)
    led.unplot(0, 3)
    led.unplot(4, 3)
    led.unplot(1, 4)
    led.unplot(2, 4)
    led.unplot(3, 4)
    basic.pause(1000)
})
```