# Comunicación por ondas de radio

## Objetivo @unplugged

Este proyecto utiliza las ondas de [radio](/reference/radio) para enviar mensajes a otros @boardname@.

**¡Muy importante!**. Este ejercicio tienes que hacerlo con otro compañero/a. Uno de vosotros tendrá el @boardname@ **emisor** y el otro el @boardname@ **receptor**.

Cuando pulses:

* el botón ``|A|`` en tu @boardname@, tus amigos verán la imagen de un **pato** 🦆 en sus @boardname@ ,
* el botón ``|B|``, verán la imagen de una **jirafa** 🦒.

![@boardname@ enviando estados de ánimo](/static/mb/projects/mood-radio.png)

## Paso 1: Programando el botón A del emisor 

Para poder comunicarse, los @boardname@ tienen que estar en el mismo **grupo**. Por ello, ``||basic: al iniciar||`` establece ``||radio: radio establecer grupo [17]||``. (Puedes elegir otro número de grupo)

Ahora, añadimos al bloque ``||input: al presionar el botón A||`` el bloque ``||radio: enviar (texto) cadena: (    )||`` . Como nombre del texto enviado puedes elegir``||radio: (mensaje_1)||``., por ejemplo.
.
Para asegurarte de que el mensaje ha sido enviado, puedes hacer que se  muestre el texto **m1* (mensaje_1) con el bloque ``||basic: mostrar cadena ||``

```blocks
radio.setGroup(17)
input.onButtonPressed(Button.A, function () {
    radio.sendString("mensaje_1")
    basic.showString("m1")
})
```

## Paso 2: Programando el botón B del emisor 

Ahora vamos a programar el botón ``||B||`` para que emita un mensaje con el texto **mensaje_2** y se confirme con el texto **m2**. 

```blocks

input.onButtonPressed(Button.B, function () {
    radio.sendString("mensaje_2")
    basic.showString("m2")
})
```

## Paso 3: Configurando el grupo del receptor

Ahora vamos a programar el @boardname@ de tu compañero o compañera. **Esto lo hará en su ordenador y en su @boardname@**.

Como ya dijimos, para poder comunicarse, los @boardname@s tienen que estar en el mismo **grupo** ``||basic: al iniciar||``.  Establece ``||radio: radio establecer grupo [17]||``. Si recordáis, escogimos el grupo número **17**.  

Ahora los dos @boardname@ se pueden comunicar porque están en el mimsmo grupo 17.


```blocks
radio.setGroup(17)

```

## Paso 4: Recibiendo el mensaje_1

Vamos a seguir programando el receptor para que reciban los dos mensajes (mensaje_1 y mensaje_2) enviados por el emisor.


Añadimos un bloque ``||radio:al recibir radio (receivedString)||`` (cadena de texto recibida) que ejecutará código cada vez que llegue un nuevo mensaje.

A continuación, colocamos el bloque condicional ``||loops: si <receivedString="mensaje_1¨¨>||`` . Eso se traduciría así "Si el texto recibido es mensaje_1".

Cuando reciba el "mensaje_1" debe mostrar el icono de un 🦆 ``||basic: mostrar icono showIcon(Pato)||``.
Haz también que que suene la ``||music: melodía||`` Dadadadum.


```blocks
radio.setGroup(17)
radio.onReceivedString(function (receivedString) {
    if (receivedString == "mensaje_1") {
        basic.showIcon(IconNames.Duck)
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Dadadadum), music.PlaybackMode.InBackground)
    }
})
```

## Paso 5: Recibiendo el mensaje_2

¿Qué ocurre si pulsamos el botón **B** en el emisor? Pues que en el @boardname@ receptor se debe mostrar el icono de una jirafa 🦒 y suene la melodía Animador.

Para hacerlo, comienza añadiendo una condición nueva haciendo click en el icono ➕ del bloque ``||loops: si||``.

Seguro que sabes terminar este paso.

```blocks
radio.onReceivedString(function (receivedString) {
    if (receivedString == "mensaje_1") {
        basic.showIcon(IconNames.Duck)
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Dadadadum), music.PlaybackMode.InBackground)
    } else if (receivedString == "mensaje_2") {
        basic.showIcon(IconNames.Giraffe)
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Entertainer), music.PlaybackMode.InBackground)
    }
})
```


## Final

Prueba el funcionamiento en el simulador.

Envía los programas a los @boardname@ emisor y receptor y prueba el funcionamiento.

## Programa completo



```package
radio
```