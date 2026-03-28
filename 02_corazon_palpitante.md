# 💖 ¡Haz que tu Micro:bit tenga sentimientos! El Corazón Palpitante

## El Reto de hoy @unplugged
¿Sabías que las pantallas de cine son solo un montón de imágenes fijas pasando muy rápido? Hoy vas a convertirte en animador. Vamos a programar los 25 LEDs de tu Micro:bit para conseguir una animación y crear un corazón que "late" de verdad.

![Animación Corazón](https://pxt.azureedge.net/blob/885698b64e03b22e7d706596395b098f98ec561d/static/mb/projects/flashing-heart.gif)

### 🎒 Requisitos (Tu Kit de Inventor)
* **1 Micro:bit** (v1 o v2).
* **1 Cable USB**.
* **Un ordenador** con acceso a MakeCode.

### 🧠 Conceptos Clave
* **Bucle "Para Siempre" (Forever):** Es un bloque verde que repite todo lo que hay dentro una y otra vez.
* **Fotograma:** Cada una de las imágenes fijas que forman una animación. Nuestra animación tendrá dos fotogramas.
* **Milisegundos (ms):** Como medimos el tiempo en programación. **1000ms = 1 segundo**.

## Paso 1: Dibuja el primer fotograma
Para que el corazón lata, primero necesitamos que aparezca en pantalla.

1. Haz clic en la categoría ``||basic:Básico||``.
2. Arrastra el bloque ``||basic:mostrar leds||`` y encájalo dentro de ``||basic:para siempre||``.
3. Dibuja un **corazón grande** haciendo clic en los cuadrados del bloque.

## Paso 2: Crea la animación
Una animación ocurre cuando mostramos una imagen grande y luego una pequeña de forma sucesiva.

1. Arrastra otro bloque ``||basic:mostrar leds||`` debajo del primero.
2. En este segundo bloque, dibuja un **corazón más pequeño** (o solo un punto en el centro).

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
