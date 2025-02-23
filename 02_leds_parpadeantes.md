# LEDs parpadeantes

## Objetivo @unplugged

Enciende y apaga un LED constantemente

```blocks
basic.forever(() => {
    led.plot(0, 0)
    basic.pause(1000)
    led.unplot(0, 0)
    basic.pause(1000)
})
```
¡Vamos 🚀!

## Paso 1

El concepto es muy simple: enciende el LED, espera un rato, apaga el LED, espera de nuevo y se repite de nuevo.

Comencemos añadiendo una línea de código que enciende el LED en la posición (0, 0) ``||led.graficar x=0, y=0||``. Colócalo dentro de `` ||basic:para siempre||`` 

```blocks
basic.forever(()=> {
    led.plot(0,0)
}
```

Prueba el programa en el simulador para asegurarte de su funcionamiento.

## Paso 2

Ahora, añadamos código para mantener el LED encendido durante 1 segundo (1000 milisegundos) ``||basic:pausa ms (1000)||`` y apagar el LED ``||led.ocultar x=0, y=0||``.

```blocks
basic.forever(() => {
    led.plot(0, 0)
    basic.pause(1000)
    led.unplot(0,0)
})
```

## Paso 3
Como ves, el funcionamiento no es correcto. Para solucionarlo añadamos otra pausa.

```blocks
basic.forever(() => {
    led.plot(0, 0)
    basic.pause(1000)
    led.unplot(0, 0)
    basic.pause(1000)
})
```
Muy bien, estás preparado para continuar con algún desafío.


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