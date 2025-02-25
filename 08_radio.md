# Mood Radio

## @description Una mini aplicación de mensajería de estados de ánimo usando la radio

![@nombredelabord@ enviando estados de ánimo](/static/mb/projects/mood-radio.png)

Este proyecto utiliza las ondas de [radio](/referencia/radio) para enviar mensajes a otor @boardname@.

Cuando pulses ``A`` en ti @boardname@, tus amigos verán un mensaje en sus @boardname@ una cara **sonriente**. Si pulsas ``B``, verán otro mensaje distinto.

## Enviar un smiley

El @boardname@ no puede entender el estado de ánimo, pero es bastante bueno con los números. De hecho, puede enviar números
entre @boardname@s usando la antena de radio, igual que un teléfono puede enviar mensajes de texto.

Vamos a añadir bloques que envíen un número cuando se pulse el botón ``A``. Suponemos que `0` es el «código de humor» para enviar **smiley**.

Bloques
radio.setGroup(1)
input.onButtonPressed(Button.A, function () {
    radio.sendNumber(0)
    basic.showIcon(IconNames.Happy)
})
```

## Recibiendo un smiley

Añadimos un bloque ``||radio:on received number||`` que ejecutará código cada vez que llegue un nuevo mensaje de «estado de ánimo».
La variable ``receivedNumber`` contiene el valor numérico que se ha enviado. Como hemos decidido que
`0` es **sonriente**, añadimos una sentencia condicional ``||logic:if then||`` para mostrar este icono.

Bloquea
radio.onReceivedNumber(function (receivedNumber) {
    if (receivedNumber == 0) {
        basic.showIcon(IconNames.Happy)
    }
})
```

## Enviando un ceño fruncido

Añadir otro estado de ánimo a nuestra aplicación de mensajería se hace de forma similar. Decidimos que el «código de humor» de `1` significa **fruncir el ceño**. Podemos añadir un evento de botón ``B`` que envíe ese código.

``bloques
input.onButtonPressed(Button.B, function () {
    radio.sendNumber(1)
    basic.showIcon(IconNames.Sad)
})
```

Si el evento ``||radio:on received number|||`` ocurre, añadimos otra sentencia condicional ``||logic:if then|||`` para manejar el «código de humor» **frowny**.

Bloquea
radio.onReceivedNumber(function (receivedNumber) {
    if (receivedNumber == 0) {
        basic.showIcon(IconNames.Happy)
    }
    if (receivedNumber == 1) {
        basic.showIcon(Iconos.Triste)
    }
})
```

Ya está. Descarga tu código en múltiples @nombredelaplataforma y ¡pruébalo!

## Desafíos

Intenta añadir un nuevo código y usa el evento ``||input:on shake||`` para enviarlo.

## Programa completo

``bloques
radio.setGroup(1)
input.onButtonPressed(Button.A, function () {
    radio.sendNumber(0)
    basic.showIcon(IconNames.Happy)
})
input.onButtonPressed(Button.B, function () {
    radio.sendNumber(1)
    basic.showIcon(Iconos.Triste)
})
radio.onReceivedNumber(function (receivedNumber) {
    if (receivedNumber == 0) {
        basic.showIcon(IconNames.Happy)
    }
    if (receivedNumber == 1) {
        basic.showIcon(Iconos.Triste)
    }
})
```

```paquete
radio
```

Traducción realizada con la versión gratuita del traductor DeepL.com