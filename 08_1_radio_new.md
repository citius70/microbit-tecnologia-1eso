# 📡 ¡Walkie-Talkie de Animales! (Mensajes por Radio)

### 🌟 El Reto de hoy
¿Sabías que tu Micro:bit tiene una "antena invisible"? Hoy vamos a aprender a usarla para enviar mensajes por el aire. Vamos a crear un sistema donde tú pulsas un botón y, ¡mágicamente!, aparecerá un animal con sonido en la placa de tu compañero/a. 

**¡Importante!**: Este reto se hace por parejas. Uno será el **Emisor** (quien envía) y el otro el **Receptor** (quien recibe).

---

### 🎒 Tu Kit de Inventor
* **2 placas Micro:bit** (una para cada uno).
* **2 cables USB** o portapilas.
* **Un compañero/a de misión.**

### 🧠 Diccionario Ninja
* **Radio:** Es una forma de enviar datos por ondas invisibles (como el Wi-Fi o el mando de la tele).
* **Grupo de Radio:** Es como el "canal" de la tele. Si no estáis en el mismo canal, ¡no os podréis escuchar!

---

## 1. Sintonizando la antena (Para los dos) 📺
Antes de hablar, tenemos que estar en la misma frecuencia. 

1.  Busca el bloque `||radio:radio establecer grupo [1]||`.
2.  Cámbialo al número **17** (o el que acordéis con el profesor).
3.  Ponlo dentro del bloque `||basic:al iniciar||`.

```blocks
radio.setGroup(17)
```

---

## 2. Misión: El Emisor (¡Tú envías!) 📤
Ahora vamos a programar los botones para que lancen mensajes al aire.

1.  Saca el bloque `||input:al presionar el botón A||`.
2.  Dentro, pon el bloque `||radio:radio enviar cadena " "||` y escribe: **mensaje_1**.
3.  Para saber que ha funcionado, añade un `||basic:mostrar cadena "m1"||`. ¡Así sabrás que el mensaje ha salido de tu placa!
4.  **Repite lo mismo para el botón B**, pero envía **mensaje_2** y muestra en pantalla **m2**.

```python
# Así debería quedar tu código de Emisor
radio.setGroup(17)

def on_button_pressed_a():
    radio.send_string("mensaje_1")
    basic.show_string("m1")
input.on_button_pressed(Button.A, on_button_pressed_a)

def on_button_pressed_b():
    radio.send_string("mensaje_2")
    basic.show_string("m2")
input.on_button_pressed(Button.B, on_button_pressed_b)
```

---

## 3. Misión: El Receptor (¡Tú escuchas!) 📥
Ahora vamos a programar la placa de tu compañero para que "entienda" lo que recibe.

1.  Busca el bloque especial `||radio:al recibir radio (receivedString)||`. Todo lo que pongas dentro ocurrirá cuando llegue un mensaje.
2.  Usa la lógica: necesitamos un bloque `||logic:si < > entonces||`.
3.  **Si** el texto recibido (`receivedString`) es igual a **"mensaje_1"**:
    * Muestra el icono del **Pato** 🦆.
    * ¡Haz que suene la melodía **Dadadadum**! 🎶
4.  Pulsa el botón **(+)** del bloque "si" para añadir una opción más (**si no, si...**).
5.  **Si** el texto es igual a **"mensaje_2"**:
    * Muestra la **Jirafa** 🦒 y haz que suene la melodía **Animador**.

```blocks
radio.onReceivedString(function (receivedString) {
    if (receivedString == "mensaje_1") {
        basic.showIcon(IconNames.Duck)
        music.play(music.builtInPlayableMelody(Melodies.Dadadadum), music.PlaybackMode.InBackground)
    } else if (receivedString == "mensaje_2") {
        basic.showIcon(IconNames.Giraffe)
        music.play(music.builtInPlayableMelody(Melodies.Entertainer), music.PlaybackMode.InBackground)
    }
})
```

---

## 4. ¡Prueba de fuego! 🔥
1.  Conectad las Micro:bit y descargad el código.
2.  Poneos a un par de metros de distancia.
3.  **Emisor:** Pulsa el botón A... ¿Ha aparecido el pato en la otra placa? 
4.  **Receptor:** ¡Alucina con el sonido y el dibujo!
