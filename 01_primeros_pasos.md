# 🚀 ¡Personaliza tu Gadget! Primeros pasos con Micro:bit 

## 🌟 El Reto de hoy @unplugged
¿Acabas de recibir tu Micro:bit? ¡Vamos a darle vida! Hoy aprenderás a programar tu placa para que sea tu **tarjeta de identificación inteligente**, un **comunicador de estados de ánimo** y un **dado electrónico** para tus juegos. 

---

### 🎒 Requisitos (Tu Kit de Inventor)
* **1 Micro:bit** (v1 o v2).
* **1 Cable USB**.
* **Un ordenador** con acceso a MakeCode.

### 🧠 Conceptos Clave
* **Eventos:** Son los "disparadores". Por ejemplo: *Al presionar un botón* o *Al agitar*. El código solo se ejecuta cuando ese evento ocurre.
* **Cadenas de texto:** Es como llamamos los programadores a las palabras o frases.
* **Azar:** Dejar que la Micro:bit elija un número por nosotros, ¡como un dado de verdad!

---

## 1. ¡Identifícate! (Al iniciar) 🪪
Lo primero es que la placa sepa quién es su dueño. Queremos que, nada más conectarla, salude con tu nombre.

1.  Busca el bloque azul `||basic:al iniciar||`.
2.  Arrastra dentro el bloque `||basic:mostrar cadena "Hola"||`.
3.  Cambia "Hola" por **TU NOMBRE**. 

```blocks
basic.showString("ALBERTO")
```


## 2. Botón A: Tu nombre a la orden 🔘
Ahora haremos que tu nombre no solo salga al principio, sino cada vez que tú quieras.

1.  Saca el bloque rosa `||input:al presionar el botón A||`.
2.  Pon dentro otro `||basic:mostrar cadena||` con tu nombre. 
3.  **Prueba:** Haz clic en el botón A del simulador. ¡Ahí está!

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showString("ALBERTO")
})
```


## 3. Botón B: ¿Cómo te sientes hoy? 😊
Vamos a usar la pantalla de 25 LEDs para mostrar un dibujo (icono).

1.  Saca el bloque `||input:al presionar el botón A||` y cámbialo a **B** usando la flechita.
2.  Arrastra dentro el bloque `||basic:mostrar LEDs||`.
3.  **Dibuja:** Haz clic en los cuadraditos para dibujar una cara sonriente o tu icono favorito.

```blocks
input.onButtonPressed(Button.B, function () {
    basic.showLeds(`
        . # . # .
        . . . . .
        # . . . #
        . # # # .
        . . . . .
        `)
})
```


## 4. ¡Agita para jugar! (El Dado Digital) 🎲
Tu Micro:bit tiene un sensor de movimiento llamado acelerómetro. Vamos a usarlo para crear un dado del 1 al 6.

1.  Busca el bloque `||input:si agitado||`.
2.  Mete dentro un `||basic:mostrar número||`.
3.  En lugar del "0", ve a **Matemática** y busca `||math:escoger al azar de 0 a 10||`.
4.  **Ajuste importante:** Cambia los números para que el azar sea de **1 a 6**.

```blocks
input.onGesture(Gesture.Shake, function () {
    basic.showNumber(randint(1, 6))
})
```

---

## 💾 Cómo pasar tu magia a la placa
¡Es hora de salir del ordenador!
1. Conecta tu Micro:bit al USB.
2. Haz clic en el botón gigante **Descargar**.
3. Si te sale una ventana, busca la unidad llamada **MICROBIT** y guarda el archivo ahí.
4. ¡Mira la parte de atrás de tu placa! Una luz amarilla parpadeará mientras se transfiere el código.

---

## 🏆 Súper Desafío (Modo Pro)
¿Crees que puedes combinarlo todo?
* Intenta que al presionar **A+B** (los dos a la vez) la Micro:bit muestre un icono de un **corazón latiendo**.
* **Pista:** Necesitarás dos bloques de `||basic:mostrar icono||` seguidos dentro de un evento de botón A+B.

---
