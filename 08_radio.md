# Comunicación por ondas de radio

##Objetivo @unplugged

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

## Paso 3: Configurando el grupo del emisor

Ahora vamos a programar el @boardname@ de tu compañero o compañera. **Esto lo hará en su ordenador y en su @boardname@**.

Como ya dijimos, para poder comunicarse, los @boardname@s tienen que estar en el mismo **grupo** ``||basic: al iniciar||``.  Establece ``||radio: radio establecer grupo [17]||``. Si recordáis, escogimos el grupo número **17**.  

Ahora los dos @boardname@ se pueden comunicar porque están en el mimsmo grupo 17.


```blocks
radio.setGroup(17)

```

## Paso 4: Recibiendo los mensajes

Vamoa a seguir programando el receptor para que reciban los dos mensajes (mensaje_1 y mensaje_2).

Añadimos un bloque ``||radio:al recibir radio (cadenaRecibida)||`` que ejecutará código cada vez que llegue un nuevo mensaje de «estado de ánimo».
La variable ``receivedNumber`` contiene el valor numérico que se ha enviado. Como hemos decidido que
`0` es **sonriente**, añadimos una sentencia condicional ``||logic:si entonces||`` para mostrar este icono.

```blocks
radio.setGroup(17)
radio.onReceivedNumber(function (receivedNumber) {
    music.setVolume(255)
    if (receivedNumber == 0) {
        basic.showIcon(IconNames.Happy)
        music.play(music.builtinPlayableSoundEffect(soundExpression.happy), music.PlaybackMode.UntilDone)
    }
})
```

## Paso 4: Recibiendo una cara enfadada 😠

¿Qué ocurre si pulsamos el botón **B**?

Si el evento ``||radio:al recibir radio (receivedNumber)|||`` ocurre, añadimos otra sentencia condicional ``||logic:si entonces|||`` para mostrar una cara enfadada.

```blocks
radio.onReceivedNumber(function (receivedNumber) {
    music.setVolume(255)
    if (receivedNumber == 0) {
        basic.showIcon(IconNames.Happy)
        music.play(music.builtinPlayableSoundEffect(soundExpression.giggle), music.PlaybackMode.UntilDone)

    }
    if (receivedNumber == 1) {
        basic.showIcon(IconNames.Sad)
        music.play(music.builtinPlayableSoundEffect(soundExpression.sad), music.PlaybackMode.UntilDone)

    }
})
```

Ya está. Descarga tu código en múltiples @nombredelaplataforma y ¡pruébalo!

## Final

Envía los programas a los @boardname@ y prueba el funcionamiento.

## Programa completo

```blocks
radio.setGroup(17)
input.onButtonPressed(Button.A, function () {
    radio.sendNumber(0)
    basic.showIcon(IconNames.Happy)
})
input.onButtonPressed(Button.B, function () {
    radio.sendNumber(1)
    basic.showIcon(IconNames.Sad)
})
radio.onReceivedNumber(function (receivedNumber) {
    music.setVolume(255)
    if (receivedNumber == 0) {
        basic.showIcon(IconNames.Happy)
        music.play(music.builtinPlayableSoundEffect(soundExpression.happy), music.PlaybackMode.UntilDone)

    }
    if (receivedNumber == 1) {
        basic.showIcon(IconNames.Sad)
        music.play(music.builtinPlayableSoundEffect(soundExpression.sad), music.PlaybackMode.UntilDone)

    }
})
```

```package
radio
```