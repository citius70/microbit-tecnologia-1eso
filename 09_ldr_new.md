# 🔦 ¡Detector de Oscuridad! Alarma y Medidor de Luz


## Objetivo @showdialog

### 🌟 El Reto de hoy
¿Sabías Micro:bit puede sentir cuánta luz hay en la habitación. Hoy vamos a programar un dispositivo que:
1.  Muestre una **gráfica de energía** en tiempo real.
2.  Te diga el **número exacto** de luz si pulsas un botón.
3.  ¡Active una **alarma sonora** cuando alguien apague las luces!

---

### 🎒 Tu Kit de Inventor
* **1 Micro:bit** y su cable USB.
* **Altavoces o auriculares** (si tu Micro:bit es la versión v1). Si es la v2, ¡ya tiene altavoz!
* **Tu mano o una linterna** para jugar con la luz.

### 🧠 Diccionario Ninja
* **LDR (Sensor de luz):** Es el componente que mide el brillo. En la Micro:bit, ¡son los propios LEDs de la pantalla los que hacen este trabajo!
* **Rango 0-255:** Es la escala de la Micro:bit. **0** es oscuridad total (cueva de lobos) y **255** es luz máxima (un foco de estadio).

---

## Paso 1: Creando una gráfica de barras 📊
Vamos a hacer que la Micro:bit nos muestre cuánta luz hay usando sus 25 LEDs como si fuera una gráfica de batería.

1.  Busca el bloque `||basic:para siempre||`.
2.  Dentro, encaja el bloque `||led:trazar gráfico de barras de [0] hasta [0]||`.
3.  En el primer hueco, pon el sensor `||input:nivel de luz||`.
4.  En el segundo hueco (el límite), escribe **255**.

> **💡 Truco:** Abre el simulador y mueve el sol que aparece arriba a la izquierda. ¡Verás cómo suben y bajan los LEDs!

```blocks
basic.forever(function () {
    led.plotBarGraph(
    input.lightLevel(),
    255
    )
})
```

---

## Paso 2: El botón de "Precisión" 🧐
A veces no nos basta con una gráfica, queremos saber el número exacto de brillo.

1.  Dentro del mismo bloque `||basic:para siempre||`, añade un bloque `||logic:si < > entonces||`.
2.  La condición será: `||input:botón A presionado||`.
3.  Si lo pulsas, haz que la placa haga un `||basic:mostrar número (nivel de luz)||`.

```blocks
basic.forever(function () {
    led.plotBarGraph(input.lightLevel(), 255)
    if (input.buttonIsPressed(Button.A)) {
        basic.showNumber(input.lightLevel())
    }
})
```

---

## Paso 3: ¡Alarma de Intrusos! 🌃
Vamos a programar la Micro:bit para que "grite" si detecta que la luz baja de un nivel (por ejemplo, si alguien cierra la puerta o apaga la luz).

1.  Añade otro bloque `||logic:si < > entonces / si no||`.
2.  La condición será: `||logic:si||` `||input:nivel de luz < 50||`.
3.  **Si es menor de 50 (está oscuro):** pon el bloque `||music:reproducir tono (Sol alto)||`.
4.  **Si no (hay luz):** pon el bloque `||music:parar todos los sonidos||`.

```blocks
basic.forever(function () {
    led.plotBarGraph(input.lightLevel(), 255)
    if (input.buttonIsPressed(Button.A)) {
        basic.showNumber(input.lightLevel())
    }
    if (input.lightLevel() < 50) {
        music.play(music.tonePlayable(784, music.beat(BeatFraction.Whole)), music.PlaybackMode.UntilDone)
    } else {
        music.stopAllSounds()
    }
})
```

---

## 🚀 ¡Pruébalo y descarga!
1.  Pulsa el botón **Descargar** y pasa el código a tu Micro:bit.
2.  Tapa la placa con tu mano... **¿Suena la alarma?** 🚨
3.  Pulsa el botón A... **¿Qué número de luz tiene tu clase ahora mismo?**

---

## 🏆 Súper Desafío (Modo Pro)
* **Ajuste de sensibilidad:** ¿Crees que 50 es demasiado poco? Intenta cambiar ese número para que la alarma suene incluso cuando hay algo de luz.
* **Aviso visual:** Haz que, además de sonar, aparezca una **calavera 💀** en los LEDs cuando la luz baje de 50.
