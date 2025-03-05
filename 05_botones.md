# Botones sonrientes

## Objetivo @showdialog

Programa los botones del @boardname@ para que muestren una cara feliz 😀 o triste 🙁

![Presionando los botones A y B](/static/mb/projects/smiley-buttons/sim.gif)

## Paso 1: Botón A = Cara alegre

Mostremos una cara feliz 😀 cuando presionemos el botón ``|A|``.

* Haga clic en la categoría ``||basic:Básico||`` en la Caja de herramientas. Arrastre el bloque ``||basic:mostrar icono|`` al bloque ``||input:al presionar el botón A||``.

    * En el bloque ``||basic:mostrar icono||``, haz clic en el ícono de la **cara alegre** para abrir el menú. Seleccione un icono de cara feliz.

* Hagamos que suene una melodía también.
    
    * Arrastra el bloque  ``||music:reproduce secuencia (feliz) en modo [hasta que termine]||``  

En el simulador @boardname@ en la pantalla, presiona el botón ``|A|``. ¿Ves una cara feliz? ⭐¡Buen trabajo! ⭐

```blocks
input.onButtonPressed(Button.A, function() { 
    basic.showIcon(IconNames.Happy)
    music.play(music.builtinPlayableSoundEffect(soundExpression.happy), music.PlaybackMode.UntilDone)
})
```

## Paso 2: Botón B = Cara triste

Ahora mostremos una cara triste 🙁 cuando presionemos el botón ``|B|``.

* Haz clic en la categoría ``||input:Entrada||`` en la Caja de herramientas.

    * Arrastra otro bloque ``||input:al presionar el botón A||`` al espacio de trabajo de codificación (puede colocarlo en cualquier lugar).

    * Haz clic en el menú desplegable del botón ``|A|`` y selecciona ``|B|``.

* Hagamos que suene una melodía también.
    
    * Arrastra el bloque  ``||music:reproduce secuencia (triste) en modo [hasta que termine]||``  


```blocks
input.onButtonPressed(Button.B, function() {
    basic.showIcon(IconNames.Sad)
    music.play(music.builtinPlayableSoundEffect(soundExpression.sad), music.PlaybackMode.UntilDone)
})
```

Presiona el botón ``|B|`` en el simulador @boardname@ en la pantalla,. ¿Ves una cara triste? ⭐¡Bien! ⭐

## Paso 3: Botón A + B

Vamos más allá: ¡intenta agregar un emoji secreto que aparece cuando se presionan los botones ``|A|`` y ``|B|`` juntos!

## Paso 4: Envía el programa al micro:bit

Conecta el @boardname@ al ordenador y haz clic en el botón ``|Descargar|``.

Sigue las instrucciones para transferir tu código a @boardname@.

Presiona los botones ``|A|`` y ``|B|`` en el micro:bit para ver tus emojis felices 😀 y tristes 🙁.


```template
input.onButtonPressed(Button.A, function() {})
```