# Dados


¡Bienvenido! Este tutorial te ayudará a crear un dado. ¡Empecemos!

## Paso 1

Vamos a crear una condición para cuando el @boardname@ sea agitado. ``||input: si [agitado]||``


```blocks
input.onGesture(Gesture.Shake, () => {
})
```

## Paso 2

Necesitamos mostrar un **valor aleatorio del 1 al 6** en nuestro dado ``||math: escoger al azar de [1] a [6]||`` y guardarlo (fijarlo) en una variable. Así que vamos a crear una variable local llamada ``||variables: puntos||``.

```blocks
input.onGesture(Gesture.Shake, () => {
    let puntos = randint(1, 6)
})
```

## Paso 3

Hagamos que se enciendan 6 LEDs ``||basic: mostrar LEDS||`` en el caso de que al agitar salga el nº 6 (``||variables: puntos = 6||``)


```blocks
input.onGesture(Gesture.Shake, () => {
    let puntos = randint(1, 6);
    if (puntos == 6) {
        basic.showLeds(`
. # . # .
. . . . .
. # . # .
. . . . .
. # . # .`);
    }
});
```

## Paso 4

Vamos a programar para que cada vez que salga el nº 6, se emita un sonido con ``||music:reproduce secuencia [risa] en modo [hasta que termine]||``

```blocks
input.onGesture(Gesture.Shake, () => {
    let puntos = randint(1, 6);
    if (puntos == 6) {
        basic.showLeds(`
. # . # .
. . . . .
. # . # .
. . . . .
. # . # .`);
music.play(music.builtinPlayableSoundEffect(soundExpression.giggle), music.PlaybackMode.UntilDone)
    }
});
```


## Paso 5

Creamos una nueva condición para cuando salga un 5. Para ello, haz que se enciendan 5 LEDs y se emita otro sonido cuando salga un 5. Coloca estos bloque dentro del espacio ``||si no||``


```blocks
input.onGesture(Gesture.Shake, ()=> {
    let puntos = randint(1, 6);
    if (puntos == 6) {
        basic.showLeds(`
. # . # .
. . . . .
. # . # .
. . . . .
. # . # .`);
music.play(music.builtinPlayableSoundEffect(soundExpression.giggle), music.PlaybackMode.UntilDone)
    }
    else if (puntos == 5) {
        basic.showLeds(`
. . . . .
. # . # .
. . # . .
. # . # .
. . . . .`);
music.play(music.builtinPlayableSoundEffect(soundExpression.happy), music.PlaybackMode.UntilDone)
    }
});

```


Ahora tenemos que repetir los mismos pasos para si **roll** es 3. Si **roll** es 3 mostraremos `4` en el dado.


``bloquea
input.onGesture(Gesture.Shake, () => {
    let tirada = randint(0, 6);
    if (tirada == 5) {
        basic.showLeds(`
. # . # .
. . . . .
. # . # .
. . . . .
. # . # .`);
    }
    else if (roll == 4) {
        basic.showLeds(`
. . . . .
. # . # .
. . # . .
. # . # .
. . . . .`);
    }
    else if (roll == 3) {
        basic.showLeds(`
. . . . .
. # . # .
. . . . .
. # . # .
. . . . .`);
    }
});
```


Repitamos también estos pasos para mostrar el 3, el 2 y el 1 en el dado. ¡Ya casi hemos terminado con nuestros dados!

```bloques
input.onGesture(Gesture.Shake, () => {
    let tirada = randint(0, 6);
    if (tirada == 5) {
        basic.showLeds(`
. # . # .
. . . . .
. # . # .
. . . . .
. # . # .`);
    }
    else if (roll == 4) {
        basic.showLeds(`
. . . . .
. # . # .
. . # . .
. # . # .
. . . . .`);
    }
    else if (roll == 3) {
        basic.showLeds(`
. . . . .
. # . # .
. . . . .
. # . # .
. . . . .`);
    }
    else if (roll == 2) {
        basic.showLeds(`
# . . . .
. . . . .
. . # . .
. . . . .
. . . . #`);
    }
    else if (roll == 1) {
        basic.showLeds(`
. . . . .
. # . . .
. . . . .
. . . # .
. . . . .`);
    }
    else {
        basic.showLeds(`
. . . . .
. . . . .
. . # . .
. . . . .
. . . . .`);
    }
});
```


## ~avatar avatar

Excelente, ¡ya estás listo para continuar con los [retos](/lecciones/dados/retos)!

## ~

Traducción realizada con la versión gratuita del traductor DeepL.com