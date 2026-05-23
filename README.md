# PeeWee car - Úkol 0 - Rozsvícení a první jízda


## Video: 
https://drive.google.com/file/d/1n8P2XIXIKbmoiksAfj6P1hJa3QwGxhln/view?usp=sharing


## Kód
```typescript
const LEDcount = 9
const strip = neopixel.create(DigitalPin.P8, LEDcount, NeoPixelMode.RGB)

basic.forever(function () {
    strip.showColor(NeoPixelColors.White) //ROZSVÍCENÍ PÁSKU
    basic.pause(5000)
    strip.clear()

    for (let i = 0; i < 5; i++) {
        PeeWeeLight.wheelSpeed(15, 15) //DOPŘEDU
        strip.showColor(NeoPixelColors.Green)
        basic.showLeds(`
        . . # . .
        . # . # .
        # . # . #
        . . # . .
        . . # . .
        `)
        basic.pause(2000)

        PeeWeeLight.wheelSpeed(-15, -15) //DOZADU
        strip.showColor(NeoPixelColors.Red)
        basic.showLeds(`
        . . # . .
        . . # . .
        # . # . #
        . # . # .
        . . # . .
        `)
        basic.pause(2000)

        PeeWeeLight.wheelSpeed(0, 0)
        strip.clear()
    }
})
```

## Sériové číslo našeho Microbita: *1404052552*