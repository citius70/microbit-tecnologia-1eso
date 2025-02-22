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

► En la categoría ``||variables:Variables||`` , click en ``Crear una variable...`` and crea una variable llamada  ``lucesOn``.

## {Mostrando LEDs - Parte 1}

En este paso, usaremos un bloque [__*si entonces / si no*__](#ifthenelse "runs some code if a Boolean condition is true and different code if the condition is false") statement.

► Desde la categoría ``||logic:Lógica||``, arrastra un bloque ``||logic:si <verdadero> entonces / si no||``  and colócalo en el contenedor ``||input:al detectar el sonido [alto]||``.  
► Busca en la categoría ``||variables:Variables||``. Encuentra la variable ``||variables:lucesOn||`` y colócala dentro del valor   ``||logic:<verdadero>||`` en la declararación ``||logic:si <verdadero> entonces / si no||`` .

```blocks
let lucesOn = 0
input.onSound(DetectedSound.Loud, function () {
    // @highlight
    if (lucesOn) {
    	
    } else {
    	
    }
})
```

## {Mostrando LEDs - Parte 2}

► Desde ``||basic:Básico||``, arrastra ``||basic:mostrar leds||`` y colócala en la **zona superior** de la declaración ``||logic:si entonces / si no||``.  
► Configura las luces como te gusten. 
💡 Por ejemplo, enciende las luces exteriores. 🎨

```blocks
let lucesOn = 0
input.onSound(DetectedSound.Loud, function () {
    if (lucesOn) {
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
💡 Esto apagará la pantalla si ``lucesOn`` no es **verdadero**.

```blocks
let lucesOn = 0
input.onSound(DetectedSound.Loud, function () {
    if (lucesOn) {
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

Al igual que accionamos un interruptor de luz, cada vez que aplaudimos, queremos **cambiar** la variable ``lucesOn`` al **opuesto** de lo que era antes.

► Desde ``||variables:Variables||``, localiza ``||variables:fijar [lucesOn] a [0]||`` y colócala en la  **zona superior** de tu contenedor ``||input:al detectar el sonido [alto] ||`` .  
► Desde la categoría ``||logic:Lógica||``, busque el operador ``||logic:not <>||`` y úselo para **reemplazar el ``[0]``** en ``||variables:fijar [lucesOn] a [0]||``.

► Desde ``||variables:Variables||``, toma ``||variables:lucesON||`` y ajústalo a la **parte vacía** del operador ``||logic:not <>||``.


```blocks
let lucesOn = false
input.onSound(DetectedSound.Loud, function () {
    // @highlight
    lightsOn = !(lucesOn)
    if (lucesOn) {
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

## {Testing in the simulator}

► Check out the simulator!  
► Click on the pink slider bar beneath the microphone icon and drag it up and down.  
💡 Right now, your @boardname@ thinks that anything above 128 is loud. Every time the sound goes > 128, your lights should switch on/off.

## {Set loud sound threshold}

Your @boardname@ might detect sounds when you don't want it to. Setting a [__*sound threshold*__](#soundThreshold "a number for how loud a sound needs to be to trigger an event. 0 = silence to 255 = maximum noise") could help 🔉🔊

► Click on the ``||input:Input||`` category. A new category should show up beneath it called ``||input:...more||``.  
► From ``||input:...more||``, grab ``||input:set [loud] sound threshold to [128]||`` and snap it into your **empty** ``||basic:on start||`` container.  
💡 Try to change the value of your sound threshold so that every time you clap, your lights will turn on if they are off and vice versa.

```blocks
// @highlight
input.setSoundThreshold(SoundThreshold.Loud, 150)
```

## {Testing, round 2}

Don't forget to test your code in the simulator!

If you have a new @boardname@ (the one with the **shiny gold** logo at the top), download this code and try it out!

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