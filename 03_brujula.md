# Brújula

Muestra la dirección a la que está orientado el @boardname@ utilizando la brújula 

## Objetivo

Mostrar la **letra N** cuando la brújula del @boardname@ apunte hacia el **Norte**.

## Paso 1

Crea un bucle que actualice constantemente la lectura de la brújula.

```blocks
basic.forever(() => {
    
})
```

Almacena la lectura en una variable llamada `grados`.
```blocks
basic.forever(() => {
    let grados = input.compassHeading()
})
```

## Paso 2

Si `grados` es **mayor que `0`** y **menor que `45`**, entonces el rumbo de la brújula apunta *mayoritariamente* hacia el **Norte**. Muestra **`N`** en el @boardname@.

```blocks
basic.forever(() => {
    let grados = input.compassHeading();
    if (grados >= 0 && grados <= 45 ) {
        basic.showString("N");
    }
});
```

## Paso 3
    
Si la brújula **no apunta hacia el Norte**, @boardname@ debe mostrar el texto **"?"**.

```blocks
basic.forever(() => {
    let degrees = input.compassHeading();
    if (degrees < 45 || degrees > 315) {
        basic.showString("N");
    }
    else {
        basic.showString("?");
    }
});
```

## Final

Enhorabuena, lo conseguiste.