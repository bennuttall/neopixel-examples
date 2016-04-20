# neopixel-examples

## Installation

```bash
sudo pip3 install rpi_ws281x
```

## Usage

Run your code with `sudo`

```python
from neopixel import Adafruit_NeoPixel

LEDS = 10
PIN = 18

strip = Adafruit_NeoPixel(LEDS, PIN)  # create your strip

strip.begin()  # this is needed before you use the strip

strip.setPixelColorRGB(0, 255, 0, 0)  # set the first pixel to red
strip.show()  # show it
```

## Examples

Turn the LEDs on, one-by-one:

```python
from time import sleep

# Turn them on (red), one-by-one
for i in range(LEDS):
    strip.setPixelColorRGB(i, 255, 0, 0)
    strip.show()
    sleep(1)

# Turn them off, one-by-one
for i in range(LEDS):
    strip.setPixelColorRGB(i, 0, 0, 0)
    strip.show()
    sleep(1)
```

Random sparkles:

```python
from time import sleep
from random import randint

while True:
    i = randint(0, LEDS-1)
    r = randint(0, 255)
    g = randint(0, 255)
    b = randint(0, 255)
    strip.setPixelColorRGB(i, r, g, b)
    strip.show()
    sleep(0.1)
```
