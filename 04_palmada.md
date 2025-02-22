# Palmas, palmitas

## {Introducción @unplugged}

El @boardname@ tiene un micrófono para detectar sonido 🎤.

Veamos como usar una palmada 👏 para encender los LEDs del @boardname@.

![Clap lights banner message](/static/mb/projects/clap-lights.png)

## {Configurando la entrada de sonido}

► Desde la categoría ``||input:Entrada||``, encuentra el contenedor ``||input:al detectar el sonido [alto]||`` y añádelo a tu trabajo.

```blocks
// @highlight
input.onSound(DetectedSound.Loud, function () {

})
```

## {Crear una variable}

Comenzamos a crear una [__*variable*__](#variable "un contenedor de información que puede cambiar") para mantener un seguimiento de si las luces están encendidas, o no.

► En la categoría ``||variables:Variables||`` , click en ``Crear una variable...`` and crea una variable llamada  ``ligtsOn``.

## {Mostrando LEDs - Parte 1}

En este paso, usaremos un bloque [__*si entonces / si no*__](#ifthenelse "runs some code if a Boolean condition is true and different code if the condition is false") statement.

► Desde la categoría ``||logic:Lógica||``, arrastra un bloque ``||logic:si <verdadero> entonces / si no||``  and colócalo en el contenedor ``||input:al detectar el sonido [alto]||``.  
► Busca en la categoría ``||variables:Variables||``. Encuentra la variable ``||variables:ligtsOn||`` y colócala dentro del valor   ``||logic:<verdadero>||`` en la declararación ``||logic:si <verdadero> entonces / si no||`` .

```blocks
let ligtsOn = 0
input.onSound(DetectedSound.Loud, function () {
    // @highlight
    if (ligtsOn) {
    	
    } else {
    	
    }
})
```

## {Mostrando LEDs - Parte 2}

► Desde ``||basic:Básico||``, arrastra ``||basic:mostrar leds||`` y colócala en la **zona superior** de la declaración ``||logic:si entonces / si no||``.  
► Configura las luces como te gusten. 
💡 Por ejemplo, enciende las luces exteriores. 🎨

```blocks
let ligtsOn = 0
input.onSound(DetectedSound.Loud, function () {
    if (ligtsOn) {
        // @highlight
    	basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
    } else {
    }
})
```

## {Limpiando la escena}

► Desde ``||basic:Básico||``, busca ``||basic:borrar la pantalla||`` y colócala en la  **zona inferior** de la declaración ``||logic:si entonces / si no||`` .  
💡 Esto apagará la pantalla si ``ligtsOn`` no es **verdadero**.

```blocks
let lightsOn = 0
input.onSound(DetectedSound.Loud, function () {
    if (ligtsOn) {
    	basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
    } else {
        // @highlight
    	basic.clearScreen()
    }
})
```

## {Configurando la variable lucesOn}

Al igual que accionamos un interruptor de luz, cada vez que aplaudimos, queremos **cambiar** la variable ``ligtsOn`` al **opuesto** de lo que era antes.

► Desde ``||variables:Variables||``, localiza ``||variables:fijar [ligtsOn] a [0]||`` y colócala en la  **zona superior** de tu contenedor ``||input:al detectar el sonido [alto] ||`` .  
► Desde la categoría ``||logic:Lógica||``, busque el operador ``||logic:not <>||`` y úselo para **reemplazar el ``[0]``** en ``||variables:fijar [ligtsOn] a [0]||``.

► Desde ``||variables:Variables||``, toma ``||variables:lucesON||`` y ajústalo a la **parte vacía** del operador ``||logic:not <>||``.


```blocks
let ligtsOn = 0
input.onSound(DetectedSound.Loud, function () {
    // @highlight
    lightsOn = !(ligtsOn)
    if (ligtsOn) {
    	basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
    } else {
    	basic.clearScreen()
    }
})
```

## {Probando en el simulador}

► Comprueba el simulador!  
► Haz click en la barra rosa bajo el icomno del micrófono y deslízala arriba y abajo.  
💡 Ahora, el @boardname@ piensa que cualquier sonido por encima del nivel 128 es alto. Cada vez que el sonido es mayor (>) de 128, las luces deberían encender/apagar.

## {Establecer el umbral de sonido alto}

 Es posible que @boardname@ detecte sonidos cuando no lo desees. Establecer un [__*umbral de sonido*__](#soundThreshold "a number for how loud a sound needs to be to trigger an event. 0 = silence to 255 = maximum noise") podría ayudar 🔉🔊

► Click en la categoría ``||input:Entrada||``. Debería aparecer una nueva categoría debajo llamada ``||input:...más||``.  
► Desde ``||input:...más||``, arastra ``||input:establecer el umbral de sonido [alto] al valor [128]||`` y colócala en tu contenedor **vacío** ``||basic:al iniciar|`` .  
💡 Intenta cambiar el valor del umbral de sonido para que cada vez que aplaudas, tus luces se enciendan si están apagadas y viceversa.

```blocks
// @highlight
input.setSoundThreshold(SoundThreshold.Loud, 150)
```

## {Probrando por 2ª vez}

No olvides probar tu código en el simulador.

Si tienes un nuevo @boardname@ (el que tiene el logo **dorado brillante** en la parte superior), ¡descarga este código y pruébalo!

```blocks
let lightsOn = false
input.onSound(DetectedSound.Loud, function () {
    lightsOn = !(lightsOn)
    if (lightsOn) {
    	basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
    } else {
    	basic.clearScreen()
    }
})
input.setSoundThreshold(SoundThreshold.Loud, 150)
```

```validation.global
# BlocksExistValidator
```

```template
//
```