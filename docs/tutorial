# 💖 ¡Haz que tu Micro:bit tenga sentimientos! El Corazón Palpitante

## El Reto de hoy @unplugged
¿Sabías que las pantallas de cine son solo un montón de imágenes fijas pasando muy rápido? Hoy vas a convertirte en animador. Vamos a programar los 25 LEDs de tu Micro:bit para conseguir una animación y crear un corazón que "late" de verdad.

![Animación Corazón](https://pxt.azureedge.net/blob/885698b64e03b22e7d706596395b098f98ec561d/static/mb/projects/flashing-heart.gif)

### 🎒 Requisitos
* **1 Micro:bit** (v1 o v2).
* **1 Cable USB**.
* **Un ordenador** con acceso a MakeCode.

### 🧠 Conceptos Clave
* **Bucle "Para Siempre" (Forever):** Repite todo lo que hay dentro una y otra vez.
* **Fotograma:** Cada una de las imágenes fijas que forman una animación. 
* **Milisegundos (ms):** Como medimos el tiempo. **1000ms = 1 segundo**.

## Paso 1: Dibuja el primer fotograma
Para que el corazón lata, primero necesitamos que aparezca en pantalla.

1. Haz clic en la categoría ``||basic:Básico||``.
2. Arrastra el bloque ``||basic:mostrar leds||`` y encájalo dentro de ``||basic:para siempre||``.
3. Dibuja un **corazón grande** haciendo clic en los cuadrados del bloque.

## Paso 2: Crea la animación
Una animación ocurre cuando mostramos una imagen grande y luego una pequeña de forma sucesiva.

1. Arrastra otro bloque ``||basic:mostrar leds||`` debajo del primero.
2. En este segundo bloque, dibuja un **corazón más pequeño**.

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

## Paso 3: Controla el ritmo
Mira el simulador a la izquierda. ¿Ves cómo late el corazón? Para que el latido sea natural, vamos a darle un respiro a la Micro:bit.

1. Coloca un bloque ``||basic:pausa (ms) 100||`` después de cada imagen.
2. Cambia el tiempo de la pausa a **500ms** para ver cómo cambia la velocidad.

```blocks
basic.forever(function() {
    basic.showLeds(`
        . # . # .
        # # # # #
        # # # # #
        . # # # .
        . . # . .`);
    basic.pause(500)
    basic.showLeds(`
        . . . . .
        . # . # .
        . # # # .
        . . # . .
        . . . . .`);
    basic.pause(500)
})
```

## Paso 4: Envía el programa a tu placa
¡Es hora de pasar tu magia a la placa real!

1. Conecta tu Micro:bit al ordenador con el cable USB.
2. Haz clic en el botón **Descargar**.
3. Sigue las instrucciones para transferir el código y mira el corazón palpitar en tu placa.

## Desafío Final
¿Quieres que tu Micro:bit sea aún más realista?

* **Añade sonido:** Haz que suene un "BUM-BUM" cada vez que el corazón cambie de tamaño usando los bloques de la categoría ``||music:Música||``.
* **Cambia el dibujo:** ¡Crea tu propia animación (una estrella que brilla, un alien, etc.)!
```

---

