# Encendido de leds

Turn an LED on and off with forever 

## Paso 1

dgsd

```sim
basic.forever(() => {
    led.plot(2, 2)
    basic.pause(500)
    led.unplot(2, 2)
    basic.pause(500)
})
```

# Psso 2