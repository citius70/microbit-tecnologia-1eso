# 🎆 ¡Espectáculo de Luces y Sonidos Aleatorios!

## 🌟 El Reto de hoy @unplugged
¿Te imaginas crear un programa que nunca se repita? Hoy vamos a programar un "generador de caos artístico". Al pulsar un botón, la Micro:bit elegirá cuántas luces encender, en qué posición y qué nota musical tocar. ¡Todo decidido por el azar!

---

### 🎒 Tu Kit de Inventor
* **1 Micro:bit** y su cable USB.
* **Altavoz o cascos** (si usas la v1).

### 🧠 Diccionario Ninja
* **Bucle (For):** Es como una orden de "repite esto X veces" para no tener que escribir el código muchas veces.
* **Azar (Randint):** Es como lanzar un dado. Le decimos a la Micro:bit: "elige un número entre el 0 y el 25".
* **Coordenadas (X, Y):** La pantalla es una cuadrícula de 5x5. Para encender un LED, hay que decirle en qué columna (X) y en qué fila (Y) está.

---

## Paso 1: ¡Prepara el Botón de Acción! 🔘
Todo el espectáculo empezará cuando pulses el **Botón A**.

1.  Saca el bloque `||input:al presionar el botón A||`.
2.  Crea una **Variable** llamada `||variables:numeroLeds||`. Aquí guardaremos cuántas luces queremos encender en cada explosión.



## Paso 2: El Bucle del Espectáculo 🔄
Queremos que el espectáculo se repita **5 veces** seguidas.

1.  Busca en **Bucles** el bloque `||loops:para index desde 0 hasta 4||` (esto lo hará 5 veces).
2.  Dentro, dile a la Micro:bit que elija cuántos LEDs encender: `||variables:establecer numeroLeds a||` `||math:escoger al azar de 0 a 25||`.



## Paso 3: ¡Encendiendo las luces y la música! 💡🎶
Ahora viene lo divertido: encender tantos LEDs como diga nuestra variable.

1.  Mete **otro bucle** dentro del anterior que vaya desde 0 hasta `||variables:numeroLeds||`.
2.  Dentro de ese segundo bucle, usa `||led:graficar x (azar 0 a 4) y (azar 0 a 4)||`. ¡Esto pondrá puntos de luz en sitios locos!
3.  Fuera del bucle de los LEDs (pero dentro del primero), añade:
    * Un bloque de **música** con un tono al azar entre **131 y 998**.
    * Una **pausa** de 500ms para que nos dé tiempo a ver las luces.
    * Un bloque de `||basic:borrar la pantalla||` para preparar la siguiente explosión.

```blocks
let numeroLeds = 0
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 5; index++) {
        numeroLeds = randint(0, 25)
        for (let index2 = 0; index2 < numeroLeds; index2++) {
            led.plot(randint(0, 4), randint(0, 4))
        }
        music.play(music.tonePlayable(randint(131, 998), music.beat(BeatFraction.Whole)), music.PlaybackMode.UntilDone)
        basic.pause(500)
        basic.clearScreen()
    }
})
```

## 🚀 ¡Pruébalo!
1.  Descarga el código y pulsa el **Botón A**.
2.  ¿Cuántos LEDs se han encendido la primera vez? ¿Y la segunda?
3.  Fíjate en los sonidos... ¡parece una computadora de una película de ciencia ficción!


## 🏆 Súper Desafío (Modo Pro)
* **Explosión rápida:** Cambia el tiempo de la pausa de 500 a 100. ¡El efecto será mucho más frenético!
