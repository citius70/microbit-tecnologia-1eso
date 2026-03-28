# 🎵 ¡El Instrumento Musical Galáctico! (Sintetizador de Movimiento)

## Objetivo @unplugged

### 🌟 El Reto de hoy
¿Alguna vez has querido crear música moviendo las manos en el aire como un mago? Hoy vamos a convertir tu Micro:bit en un **Sintetizador Espacial**. El sonido cambiará de tono y forma dependiendo de cómo inclines la placa. ¡Prepárate para crear sonidos de películas de alienígenas!

---

### 🎒 Tu Kit de Inventor
* **1 Micro:bit**
* **Tus reflejos:** ¡Tendrás que mover la placa con precisión!

### 🧠 Diccionario Ninja
* **Acelerómetro:** El sensor que detecta si inclinas la placa a la izquierda (**Eje X**) o hacia adelante (**Eje Y**).
* **Frecuencia:** Es lo que hace que un sonido sea muy grave (como un trueno) o muy agudo (como un pajarito).
* **Sintetizador:** Una máquina que crea sonidos desde cero usando matemáticas.

---

## 1. Preparando la "Voz" de la Micro:bit 🗣️
En lugar de usar melodías grabadas, vamos a fabricar un sonido único que cambie constantemente.

1.  Busca el bloque `||basic:para siempre||`.
2.  Dentro, pon el bloque de música: `||music: reproduce secuencia () en modo [hasta que termine]||`.
3.  Haz clic en `|+|` del bloque de la expresión para abrir el **Editor de Sonidos avanzado**.

---

## 2. Conectando los sensores al sonido 🎢
Aquí viene la magia. Vamos a decirle a la Micro:bit que use su movimiento para decidir qué nota tocar.

1.  En el hueco de **Frecuencia Inicial**, pon: `||input:aceleración (mg) X||` multiplicado por **50**. (Esto hace que al inclinar a los lados el sonido cambie).
2.  En el hueco de **Frecuencia Final**, pon: `||input:aceleración (mg) Y||` multiplicado por **50**. (Esto hace que al inclinar adelante y atrás el sonido varíe).
3.  Para que el sonido sea más loco, usaremos el bloque `||math:escoger al azar de 150 a 255||` en el volumen o la duración.

```blocks
basic.forever(function () {
    music.play(music.createSoundExpression(
        WaveShape.Sine,
        input.acceleration(Dimension.X) * 50,
        input.acceleration(Dimension.Y) * 50,
        randint(150, 255),
        255,
        randint(80, 100),
        SoundExpressionEffect.None,
        InterpolationCurve.Linear
    ), music.PlaybackMode.UntilDone)
})
```

---

## 3. ¡Conviértete en DJ Espacial! 🎧
1.  **Descarga** el código en tu Micro:bit.
2.  Sostén la placa plana en tu mano. Escucharás un sonido constante.
3.  **Inclínala lentamente a la izquierda:** El sonido se volverá más grave o agudo.
4.  **Inclínala hacia adelante:** ¡El sonido empezará a transformarse!
5.  Prueba a hacer movimientos circulares para crear un efecto de "platillo volante".
6.  Intenta simular el sonido de un pájaro cantando.

---

## 🚀 Súper Desafío (Modo Pro)
* **Cambio de forma:** En el código, busca donde dice `WaveShape.Sine` (Onda Senoidal) y cámbialo por `Square` (Cuadrada) o `Sawtooth` (Diente de sierra). ¿A que ahora suena mucho más "robótico" y agresivo?
