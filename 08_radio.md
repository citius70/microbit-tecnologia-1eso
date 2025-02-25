# Comunicación por ondas de radio

## Una mini aplicación de mensajería usando la radio

![@boardname@ enviando estados de ánimo](/static/mb/projects/mood-radio.png)

Este proyecto utiliza las ondas de [radio](/reference/radio) para enviar mensajes a otros @boardname@.

Cuando pulses el botón **``A``** en tu @boardname@, tus amigos verán un mensaje en sus @boardname@ una cara **sonriente**😀. Si pulsas **``B``**, verán otro mensaje distinto.

## Paso 1: Enviando un smiley 😀

El @boardname@ no puede entender el estado de ánimo, pero es bastante bueno con los números. De hecho, puede enviar números
entre @boardname@s usando la antena de radio, igual que un teléfono puede enviar mensajes de texto.

Para poder comunicarse, los @boardname@ tienen que estar en el mismo **grupo**. Por ello, al iniciar establece ``||radio: radio establecer grupo [17]||``. (Puedes elegir otro número de grupo)

Ahora, añadimos bloques que envíen un número determinado cuando se pulse el botón **``A``**. Suponemos que **`0`** es el «código de humor» para enviar **smiley**.😀

```blocks
radio.setGroup(17)
input.onButtonPressed(Button.A, function () {
    radio.sendNumber(0)
    basic.showIcon(IconNames.Happy)
})
```
## Paso 2: Enviando una cara enfadada 😠

Añadir otro estado de ánimo a nuestra aplicación de mensajería se hace de forma similar. Decidimos que el «código de humor» de `1` significa **cara enfadada**. Podemos añadir un evento de botón ``B`` que envíe ese código.

```blocks
input.onButtonPressed(Button.B, function () {
    radio.sendNumber(1)
    basic.showIcon(IconNames.Sad)
})
```

## Paso 3: Recibiendo un smiley 😀

Ahora vamos a programar el @boardname@ de tu compañero o compañera. Establece el mismo número de grupo al iniciar (en este caso, 17). 

Añadimos un bloque ``||radio:al recibir radio||`` que ejecutará código cada vez que llegue un nuevo mensaje de «estado de ánimo».
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