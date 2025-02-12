# blink blocks activity

Turn an LED on and off with forever 

## ~avatar avatar

```sim
basic.forever(() => {
    led.plot(2, 2)
    basic.pause(500)
    led.unplot(2, 2)
    basic.pause(500)
})
```
Let's build a blinking light!
