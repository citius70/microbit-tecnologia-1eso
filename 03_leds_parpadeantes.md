# LEDs parpadeantes

## Objetivo @unplugged

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

## Encender un LED

El concepto es muy simple:
1. **Enciende** el LED, **espera** un rato.
2. **Apaga** el LED, **espera** de nuevo
3. Repite de nuevo, una y otra vez.

Comencemos 🚀🚀🚀 añadiendo una línea de código que *enciende el LED en la posición (0, 0)*.
* Para ello, utiliza ``||led.graficar x=0, y=0||`` y colócalo dentro de ``||basic.para siempre||``.

```blocks
basic.forever(() => {
    led.plot(0, 0)
})
```

Prueba el programa en el simulador para asegurarte de su funcionamiento.

## Esperar, apagar el LED y volver a encender

Código para **apagar**:
1. Añade código para **pausar 1 segundo** (1000 milisegundos) : ``||basic.pausa ms(1000)||``.
2. **Apaga** el LED:  ``||led.ocultar x=0, y=0||``

Código para **volver a encender**:
1. Añade código para **pausar 1 segundo** (1000 milisegundos) : ``||basic.pausa ms(1000)||``.
2. Como el código se vuelve a repetir en este punto, el LED se volverá a encender.

```sim
basic.forever(() => {
    led.plot(0, 0)
    basic.pause(1000)
    led.unplot(0, 0)
    basic.pause(1000)
    
})
```

```blocks
    basic.forever(() => {
    led.plot(0, 0)
    basic.pause(1000)
    led.unplot(0,0)
    basic.pause(1000)
})
```


## ~avatar @unplugged

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
