---
title: "Using GPIO Pins for Input"
teaching: 20
exercises: 20
questions:
- "How can GPIO pins get information in?"
objectives:
- "GPIO pins can detect change of state"
keypoints:
- "The GPIO only has digital pins."
---
Just like with the Arduino, you can detect events using the digital pins on the Raspberry Pi. If you leave the LED wired to pin 17 and connect the button to pin 3, you can detect the button press and turn the LED on with the GPIO Zero library.

<a href="{{ page.root }}/fig/Button_with_Raspberry_Pi_MEDIUM.jpg">
  <img src="{{ page.root }}/fig/Button_with_Raspberry_Pi_FULL.jpg" alt="Button with Raspberry Pi" />
</a>

~~~
#! /usr/bin/env python3

from gpiozero import LED, Button
from signal import pause

led = LED(17)
button = Button(3)

button.when_pressed = led.on
button.when_released = led.off

pause()
~~~
{: .language-python}

In this example, the LED stays lit as long as the button is pressed. But you could just as easily have each button press turn it on or off.

Some analog devices come with a "digital pin" that works with a threshold, meaning that if the value being measured exceeds some target, the pin turns on. Sometimes this is sufficient, e.g. an alarm. Or a trigger. For actually collecting analog data, however, you would need to use an analog-to-digital converter. Or select a sensor that communicates over a serial interface.

{% include links.md %}
