# 💌 Mensajería Mágica: Love is in the air!

### 🌟 El Reto de hoy
¿Te imaginas enviar un dibujo por el aire sin usar cables? Hoy vamos a programar tu Micro:bit para que actúe como una antena de mensajes. Cuando pulses un botón, tu placa dirá **"ENVIADO"** y, en la placa de tu compañero/a, ¡aparecerá un corazón!

**Misión por parejas:** Uno será el **Emisor** y otro el **Receptor**.

---

### 🎒 Tu Kit de Inventor
* **2 placas Micro:bit**.
* **2 cables USB** o portapilas.
* **Un compañero/a de misión.**

### 🧠 Diccionario Ninja
* **Radio:** La forma en la que las Micro:bit se hablan sin tocarse.
* **Cadena (String):** Es una palabra o frase secreta que viaja por el aire. Nuestra palabra clave será "AMOR".

---

## 1. ¡Sincroniza vuestras placas! 📟
Para que vuestros mensajes no se mezclen con los de otros compañeros, tenéis que elegir vuestro propio canal.

1.  En el bloque `||basic:al iniciar||`, busca en la sección de Radio: `||radio:radio establecer grupo [1]||`.
2.  Elegid un número secreto (por ejemplo, el **42**). ¡Los dos tenéis que poner el mismo!

```blocks
radio.setGroup(42)
```

---

## 2. El Emisor (¡Tú lanzas el mensaje!) 🚀
Vamos a programar el botón para que avise cuando el mensaje ha salido.

1.  Saca el bloque `||input:al presionar el botón A||`.
2.  Busca en Radio: `||radio:radio enviar cadena " "||`.
3.  Escribe dentro de las comillas la palabra clave: **mensaje**.
4.  Para confirmar que ha funcionado, añade: `||basic:mostrar cadena "ENVIADO"||`.

```blocks
input.onButtonPressed(Button.A, function () {
    radio.sendString("mensaje")
    basic.showString("ENVIADO")
})
```

---

## 3. El Receptor (¡Tú atrapas el corazón!) 🎯
Ahora configuramos la otra placa para que reaccione cuando detecte la palabra clave en el aire.

1.  Busca el bloque: `||radio:al recibir radio (receivedString)||`.
2.  Dentro, simplemente pon: `||basic:mostrar icono (Corazón)||`.
3.  ¡Opcional! Añade un sonido para que el aviso sea total: `||music:comenzar melodía (Ringtone)||`.

```blocks
radio.onReceivedString(function (receivedString) {
    basic.showIcon(IconNames.Heart)
    music.play(music.builtInPlayableMelody(Melodies.Ringtone), music.PlaybackMode.InBackground)
})
```

---

## 4. ¡Prueba el invento! 🔥
1.  Conectad las Micro:bit y pulsad el botón **Descargar**.
2.  **Emisor:** Pulsa el botón A. Verás el texto "ENVIADO" recorriendo tu pantalla.
3.  **Receptor:** ¡Mira tu pantalla! Un corazón debería haber aparecido mágicamente con música.

---
