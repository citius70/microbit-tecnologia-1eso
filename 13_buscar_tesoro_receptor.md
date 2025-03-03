# Buscar el tesoro

## Receptor

```blocks
let signal = 0
radio.setGroup(1)
radio.onReceivedString(function (receivedString) {
    signal = radio.receivedPacket(RadioPacketProperty.SignalStrength)
    led.plotBarGraph(
    Math.map(signal, -95, -42, 0, 9),
    9
    )
})
```
