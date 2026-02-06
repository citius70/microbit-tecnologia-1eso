# Corazón palpitante

## Objetivo @showdialog

En este programa debes programar los **LEDs** en el @boardname@ para conseguir esta animación 💖

![Heart shape in the LEDs](/static/mb/projects/flashing-heart/sim.gif)

## Configura los LEDs

1. Haz clic en la categoría ``||basic:Básico||`` en la Caja de Herramientas. 

2. Arrastra el bloque ``||basic:mostrar leds||`` dentro del bloque ``||basic:para siempre||``. 

3. Después en el bloque ``||basic:mostrar leds||``, haz clic en los cuadrados para dibujar un corazón.

![An animation that shows how to drag a block and paint a heart](/static/mb/projects/flashing-heart/showleds.gif)

## Crea la animación

1. Arrastra otro bloque ``||basic: mostrar leds||``  debajo del primero y dibuja un corazón más pequeño.

```blocks
basic.forever(function() {
    basic.showLeds(`
        . # . # .
        # # # # #
        # # # # #
        . # # # .
        . . # . .`);
    basic.showLeds(`
        . . . . .
        . # . # .
        . # # # .
        . . # . .
        . . . . .`);
})
```

## Ya casi está...

Mira el @boardname@ en la pantalla. ¿Ves la animación del corazón? ⭐ ¡Buen trabajo! ⭐ 

## Vamos a darle una pausa entre latidos

1. Coloca un bloque ``||basic: pausa ms (1000)||`` después de cada imagen para ralentizar el paso de una a otra.

```blocks
basic.forever(function() {
    basic.showLeds(`
        . # . # .
        # # # # #
        # # # # #
        . # # # .
        . . # . .`);
    basic.pause(1000)
    basic.showLeds(`
     . . . . .
    . # . # .
    . # # # .
     . . # . .
    . . . . .`);
    basic.pause(1000)
})
```

## Envía el programa a @boardname@

Ahora conecta tu dispositivo @boardname@ al ordenador y haz clic en el botón ``|Descargar|``.

Sigue las instrucciones para transferir el código al @boardname@ y mira el corazón palpitar. 
