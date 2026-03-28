# 💖 ¡Haz que tu Micro:bit tenga sentimientos\! El Corazón Palpitante

## 🌟 El Reto de hoy @unplugged

¿Sabías que las pantallas de cine son solo un montón de imágenes fijas pasando muy rápido? Hoy vas a convertirte en animador. Vamos a programar los 25 LEDs de tu Micro:bit para conseguir esta animación 💖 y crear un corazón que "late" de verdad.

![Heart shape in the LEDs](/static/mb/projects/flashing-heart/sim.gif)

-----

### 🎒 Requisitos (Tu Kit de Inventor)

  * **1 Micro:bit** (v1 o v2).
  * **1 Cable USB**.
  * **Un ordenador** con acceso a MakeCode.

### 🧠 Diccionario Ninja

  * **Bucle "Para Siempre" (Forever):** Es un bloque verde que repite todo lo que hay dentro una y otra vez, como un círculo que nunca termina.
  * **Fotograma:** Cada una de las imágenes fijas que forman una animación. Nuestra animación tendrá dos fotogramas: corazón grande y corazón pequeño.
  * **Milisegundos (ms):** Es como medimos el tiempo en programación. **1000ms** equivalen a **1 segundo**.

-----

## 1. Configura los LEDs (Dibuja el primer "Fotograma") 🖍️

Para que el corazón lata, primero necesitamos que aparezca en pantalla.

1.  Haz clic en la categoría `||basic:Básico||` de tu caja de herramientas.
2.  Arrastra el bloque `||basic:mostrar leds||` y encájalo dentro de `||basic:para siempre||`.
3.  Después en el bloque `||basic:mostrar leds||`, haz clic en los cuadrados para dibujar un **corazón grande**.



## 2. Crea la animación (El segundo fotograma) 



Una animación ocurre cuando mostramos una imagen grande y luego una pequeña muy rápido.

1.  Arrastra otro bloque `||basic: mostrar leds||` debajo del primero y dibuja un **corazón más pequeño** (o solo un punto en el centro).


<!-- end list -->

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

-----

## 3. Ya casi está... (Vamos a darle una pausa entre latidos) ⏱️

Mira el simulador. ¿Ves cómo late el corazón? ⭐ ¡Buen trabajo\! ⭐ Pero a lo mejor va demasiado rápido, ¡como si estuviera asustado\! Vamos a controlar el ritmo.

Para que el latido sea natural, vamos a darle un respiro a la Micro:bit entre imagen e imagen.

1.  Coloca un bloque `||basic:pausa ms (1000)||` después de cada imagen para ralentizar el paso de una a otra.

<!-- end list -->

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

> **Dato curioso:** Si dejas la pausa en 1000ms, el corazón latirá una vez por segundo. Si la cambias a 500ms, ¡irá al doble de velocidad\!

-----

## 💾 Envía el programa a micro:bit

¡Es hora de salir del ordenador y pasar tu magia a la placa\!

1.  Conecta tu Micro:bit al ordenador con el cable USB y haz clic en el botón `|Descargar|`.
2.  Sigue las instrucciones para transferir el código a la unidad **MICROBIT** y mira el corazón palpitar en tu placa.

-----

## 🚀 Súper Desafío (Modo Pro)

¿Quieres que tu Micro:bit sea aún más realista?

  * **Añade sonido:** Haz que suene un "BUM-BUM" cada vez que el corazón cambie de tamaño usando los bloques de `||music:Música||`.

