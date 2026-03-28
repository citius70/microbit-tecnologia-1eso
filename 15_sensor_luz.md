# 💡 ¡Luz Nocturna Automática con Alarma!

## 🌟 El Reto de hoy @unplugged
¿Alguna vez te has preguntado cómo sabe una farola que debe encenderse cuando anochece? ¡Hoy vas a programar tu Micro:bit para que haga lo mismo! Vamos a crear un sensor que, en cuanto detecte oscuridad, encienda una luz de seguridad y haga sonar una pequeña alerta.

---

### 🎒 Tu Kit de Inventor
* **1 Micro:bit** (v1 o v2).
* **1 Cable USB**.
* **Tu mano** (para hacer sombra y simular la noche).

### 🧠 Diccionario Ninja
* **Nivel de Luz:** La Micro:bit mide la luz de 0 (oscuridad total) a 255 (mucha luz).
* **Condicional (Si... Entonces):** Es una regla. *Si* pasa algo (está oscuro), *entonces* la placa hace una acción (brillar).
* **Umbral (Threshold):** Es el "número mágico". En este caso usaremos el **100**. Si la luz baja de 100, ¡se activa la magia!

---

## 1. El bucle de vigilancia 🔄
Queremos que la Micro:bit esté vigilando la luz todo el tiempo, sin parar.

1.  Busca el bloque `||basic:para siempre||`. Todo lo que pongas dentro se repetirá hasta que desconectes la placa.

## 2. La gran decisión (Lógica) ⚖️
Ahora vamos a darle "cerebro" a la placa para que decida qué hacer.

1.  Ve a la categoría **Lógica** y busca el bloque `||logic:si < > entonces / si no||`.
2.  En el hueco del "si", pon una comparación: `||logic: < ||`.
3.  A la izquierda de la comparación, pon el sensor `||input:nivel de luz||`.
4.  A la derecha, escribe el número **100**.

> *Traducción para humanos:* "Si el nivel de luz es menor que 100..."

## 3. ¡Que se haga la luz y el sonido! 🔊✨
¿Qué queremos que pase cuando esté oscuro (menos de 100)?

1.  Dentro de la primera parte del "si", añade el bloque de sonido: `||music:reproducir sonido (el que más te guste)||`.
2.  Justo debajo, añade `||basic:mostrar LEDs||` y dibuja un cuadrado relleno o un rombo para que sirva de lámpara.

## 4. Apagar cuando salga el sol ☀️
Si hay luz (más de 100), no queremos gastar batería.

1.  En la parte del `||logic:si no||`, añade el bloque `||basic:borrar la pantalla||`. ¡Así los LEDs se apagarán solos!

```blocks
basic.forever(function () {
    if (input.lightLevel() < 100) {
        music.play(music.createSoundExpression(WaveShape.Sine, 5000, 0, 255, 0, 500, SoundExpressionEffect.None, InterpolationCurve.Linear), music.PlaybackMode.UntilDone)
        basic.showLeds(`
            . # # # .
            # # # # #
            # # # # #
            # # # # #
            . # # # .
            `)
    } else {
        basic.clearScreen()
    }
})
```

---

## 🚀 ¡Pruébalo!
1.  Descarga el programa en tu placa.
2.  **Tapa la Micro:bit con tu mano** para que no le llegue luz. ¿Suena la música? ¿Se encienden los LEDs?
3.  **Quita la mano.** ¡Debería quedarse en silencio y apagada!

---

## 🏆 Súper Desafío (Modo Pro)
* **Ajuste de sensibilidad:** Si tu clase tiene mucha luz, quizás el 100 no funcione bien. Intenta cambiarlo a 50 o 150 para ver cuál es el "punto perfecto" de tu sensor.
* **Modo Ahorro:** ¿Podrías hacer que, en lugar de un sonido largo, solo dé un pequeño "pitido" una vez cuando detecte oscuridad?

---

**¿Te gustaría que hagamos un tutorial para crear un "Termómetro de Colores" que te avise si hace demasiado calor en clase?**
