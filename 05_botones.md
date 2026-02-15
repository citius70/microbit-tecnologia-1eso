# Botones sonrientes

## Objetivo @showdialog

Programa los botones ``|A|`` y ``|B|`` del @boardname@ para que muestren una **cara feliz** 😀 o **triste** 🙁

![Presionando los botones A y B](/static/mb/projects/smiley-buttons/sim.gif)

## Botón A = Cara alegre

**Objetivo**: Mostremos una **cara feliz** 😀 cuando presionemos el **botón** ``|A|``.

**Instrucciones**:
1. Haz clic en la categoría ``||input:Entrada||`` en la **caja de herramientas**.
   * Arrastra  el bloque ``||input:al presionar el botón A||`` y, a continuación, el bloque ``||basic:mostrar icono|`` dentro de aquel.
2. Haz clic en ``||basic:mostrar icono||`` y selecciona la **cara alegre** .

Hagamos que **suene una melodía** también:
1. Arrastra el bloque  ``||music:reproduce secuencia (feliz) en modo [hasta que termine]||``  

**Prueba**:
En el simulador @boardname@ en la pantalla, presiona el botón ``|A|``. ¿Ves una cara feliz? ⭐¡Buen trabajo! ⭐

```blocks
input.onButtonPressed(Button.A, function() { 
    basic.showIcon(IconNames.Happy)
    music.play(music.builtinPlayableSoundEffect(soundExpression.happy), music.PlaybackMode.UntilDone)
})
```

## Botón B = Cara triste

**Instrucciones**:
1. Haz clic en la categoría ``||input:Entrada||`` en la **caja de herramientas**.
   * Arrastra  el bloque ``||input:al presionar el botón B||`` y, a continuación, el bloque ``||basic:mostrar icono|`` dentro de aquel.
2. Haz clic en ``||basic:mostrar icono||`` y selecciona la **cara triste** .

Hagamos que **suene una melodía** también:
1. Arrastra el bloque  ``||music:reproduce secuencia (triste) en modo [hasta que termine]||``  

  **Prueba**:
En el simulador @boardname@ en la pantalla, presiona el botón ``|A|`` y ``|B|`` . ¿Ves una cara feliz? ¿Ves una cara triste? ⭐¡Buen trabajo! ⭐

`  


```blocks
input.onButtonPressed(Button.B, function() {
    basic.showIcon(IconNames.Sad)
    music.play(music.builtinPlayableSoundEffect(soundExpression.sad), music.PlaybackMode.UntilDone)
})
```


## Desafío: Botón A + B

Vamos más allá: ¡intenta agregar un emoji secreto que aparece cuando se **presionan a la vez los botones** ``|A|`` y ``|B|``!

## Envía el programa al micro:bit

1. Conecta el @boardname@ al ordenador y haz clic en el botón ``|Descargar|``.

2. Sigue las instrucciones para transferir tu código a @boardname@.

3. Presiona los botones ``|A|`` y ``|B|`` en el micro:bit para ver tus emojis felices 😀 y tristes 🙁.
