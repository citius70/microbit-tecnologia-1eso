# Botones sonrientes

## ¡Codifica un emoji de micro:bit! @unplugged

Programa los botones del @boardname@ para que muestren una cara feliz 😀 o triste 🙁

![Presionando los botones A y B](/static/mb/projects/smiley-buttons/sim.gif)

## {Paso 1}

Mostremos una cara feliz 😀 cuando presionemos el botón **A**.
Haga clic en la categoría ``||basic:Básico||`` en la Caja de herramientas. Arrastre un bloque ``||basic:mostrar icono|`` al bloque ``||input:al presionar el botón A||``.
En el bloque ``||basic:mostrar icono||``, haga clic en el ícono del corazón para abrir el menú. Seleccione un icono de cara feliz.

```blocks
input.onButtonPressed(Button.A, function() { 
    basic.showIcon(IconNames.Happy)
})
```

## {Paso 2}

En el simulador @boardname@ en la pantalla, presione el botón **A**. ¿Ves una cara feliz? ⭐¡Buen trabajo! ⭐

## {Paso 3}

Ahora mostremos una cara triste 🙁 cuando presionemos el botón **B**.
Haga clic en la categoría ``||input:Entrada||`` en la Caja de herramientas.
Arrastre otro bloque ``||input:al presionar el botón A||`` al espacio de trabajo de codificación (puede colocarlo en cualquier lugar).
Haga clic en el menú desplegable del botón **A** y seleccione **B**.

```blocks
input.onButtonPressed(Button.B, function() {})
```

## {Paso 4}

Desde la categoría ``||basic:Básico||``, arrastre otro bloque ``||basic:mostrar icono||`` al bloque ``||input:al presionar el botón B||``.
En este bloque ``||basic:mostrar icono||``, haga clic en el ícono del corazón para abrir el menú.
Seleccione un icono de cara triste.

```blocks
input.onButtonPressed(Button.B, function() {
    basic.showIcon(IconNames.Sad)
})
```
## {Paso 5}

En el simulador @boardname@ en la pantalla, presione el botón **B**. ¿Ves una cara triste? ⭐¡Buen trabajo! ⭐

## {Paso 6}

Vamos más allá: ¡intenta agregar un emoji secreto que aparece cuando se presionan los botones **A** y **B** juntos!

## {Paso 7}

Si tienes un dispositivo @boardname@, conéctelo a su computadora y haga clic en el botón ``|Descargar|``. Sigue las instrucciones para transferir tu código a @boardname@. Intenta presionar los botones **A** y **B** en el micro:bit para ver tus emojis felices 😀 y tristes 🙁.


```template
input.onButtonPressed(Button.A, function() {})
```