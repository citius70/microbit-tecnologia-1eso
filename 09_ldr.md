# Medidor de Nivel de Luz

## Introducción @unplugged

Este programa utiliza el **sensor de luz** (LDR) del @boardname@ para:

* visualizar gráficamente el **nivel de luz** ambiental,
* crear una **alarma** que se accione cuando la *luz ambiental disminuya*.


## Paso 1: Trazar el nivel de luz en una gráfica

Dentro del bloque ``||basic:para siempre||`` vamos a  ``||led:trazar un gráfico de barras||`` que muestre el nivel de  ``||input:nivel de luz||``. 

El sensor de luz del @boardname@ nos devuelve el valor:

* 0 (mínimo) cuando se encuentra en total oscuridad

* 255 (máximo) cuando la luz ambiental es máxima.

Por ello, establece el límite de la grafica en 255 para que conincida con el valor máximo medido por el sensor.

```blocks
basic.forever(function () {
    led.plotBarGraph(
    input.lightLevel(),
    255
    )
    }
})
```

Mira el simulador y observa como cambia el gráfico de barras mientras ajustas el control del nivel de luz.

## Paso 2: Mostrar la lectura como número

Vamos a mostrar el nivel de luz en números (de 0 a 255) cuando pulsemos el botón ``|A|``.

Añade el código a ``||basic:enseñar un número||`` para el valor ``||input:nivel de luz||``
``|logic:si||`` se pulsa el ``||input:botón A||``.

```blocks
basic.forever(function () {
    led.plotBarGraph(
    input.lightLevel(),
    255
    )
    if (input.buttonIsPressed(Button.A)) {
        basic.showNumber(input.lightLevel())
    }
})
```

## Paso 3: Establecer una alarma cuando oscurezca



## Descarga y prueba

Descarga el código en tu @boardname@ y ¡mide el nivel de luz a tu alrededor!
