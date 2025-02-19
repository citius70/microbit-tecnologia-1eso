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

## {Displaying LEDs part 1}

In this step, we'll be using an [__*if then / else*__](#ifthenelse "runs some code if a Boolean condition is true and different code if the condition is false") statement.

► From the ``||logic:Logic||`` category, grab an ``||logic:if <true> then / else||`` block and snap it into your ``||input:on [loud] sound||`` container.  
► Look in the ``||variables:Variables||`` category. Find the new ``||variables:lightsOn||`` variable and snap it in to **replace** the ``||logic:<true>||`` value in your ``||logic:if <true> then / else||`` statement.

```blocks
let lightsOn = 0
input.onSound(DetectedSound.Loud, function () {
    // @highlight
    if (lightsOn) {
    	
    } else {
    	
    }
})
```

## {Displaying LEDs part 2}

► From ``||basic:Basic||``, grab ``||basic:show leds||`` and snap it into the **top container** of your ``||logic:if then / else||`` statement.  
► Set the lights to a pattern you like!  
💡 In the hint, we chose to turn on all of the outside lights. Feel free to make your own design 🎨

```blocks
let lightsOn = 0
input.onSound(DetectedSound.Loud, function () {
    if (lightsOn) {
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

## {Clearing the screen}

► From ``||basic:Basic||``, find ``||basic:clear screen||`` and snap it into the **bottom container** of your ``||logic:if then / else||`` section.  
💡 This will turn the display off if ``lightsOn`` is **not** ``true``.

```blocks
let lightsOn = 0
input.onSound(DetectedSound.Loud, function () {
    if (lightsOn) {
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

## {Setting the lightsOn variable}

Just like we'd toggle a light switch, each time we clap, we want to **flip** the variable ``lightsOn`` to the **opposite** of what it was before.

► From ``||variables:Variables||``, locate ``||variables:set [lightsOn] to [0]||`` and snap it in at the **very top** of your ``||input:on [loud] sound||`` container.  
► From the ``||logic:Logic||`` category, find the ``||logic:not <>||`` operator and use it to **replace the ``[0]``** in ``||variables:set [lightsOn] to [0]||``.  
► From ``||variables:Variables||``, grab ``||variables:lightsOn||`` and snap it into the **empty part** of the ``||logic:not <>||`` operator.

```blocks
let lightsOn = false
input.onSound(DetectedSound.Loud, function () {
    // @highlight
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