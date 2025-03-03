```blocks
radio.setGroup(1)
radio.setTransmitPower(1)
basic.forever(function () {
    radio.sendString("1")
    basic.pause(200)
})
```

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