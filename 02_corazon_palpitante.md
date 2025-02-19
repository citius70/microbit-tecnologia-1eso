# Corazón palpitante

## Programa un corazón palpitante @unplugged

Codifica los LEDs en el @boardname@ para conseguir esta animación 💖

![Heart shape in the LEDs](/static/mb/projects/flashing-heart/sim.gif)

## {Paso 1 @fullscreen}

Haz clic en la categoría ``||basic:Básico||`` en la Caja de Herramientas. 
Arrastra el bloque ``||basic:mostrar leds||`` dentro del bloque ``||basic:para siempre||``. 
Después en el bloque ``||basic:mostrar leds||``, haz clic en los cuadrados para dibujar un corazón.

![An animation that shows how to drag a block and paint a heart](/static/mb/projects/flashing-heart/showleds.gif)

## {Paso 2}

Arrastra otro bloque ``||basic: mostrar leds||``  debajo del primero.

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
        . . . . .
        . . . . .
        . . . . .
        . . . . .`);
})
```

## {Paso 3}

Mira el @boardname@ en la pantalla. ¿Ves la animación del corazón? ⭐ ¡Buen trabajo! ⭐ 

## {Paso 4}

Ahora conecta tu dispositivo @boardname@ al ordenador y haz clic en el botón ``|Descargar|``. Sigue las instrucciones para transferir el código al @boardname@ y mira el corazón palpitar. 

## {Paso 5}

Vamos más allá. Intenta añadir más bloques ``||basic:mostrar leds||`` para crear a animación más completa.
```template
basic.forever(function() {})
```
