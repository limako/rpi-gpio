---
title: "Using GPIO Pins for Output"
teaching: 20
exercises: 20
questions:
- "How can you use pins to control things?"
objectives:
- "Learn how to control digital pins via python."
keypoints:
- "You can signal with digital pins."
- "Don't try to power things with digital pins."
---

If you can turn a digital pin, you can use that as a signal to turn on other devices. You should generally not try to power devices (beyond an LED) using the digital pins, which you should use for signaling.

For low power devices, like small stepper motors or servos, you can deploy a transistor or relay that can use use an electrical signal to open or close a switch to a power source.

A typical transistor has three elements the positive side, connected to the electrical source, a negative side, than will be connected in series with the element to be powered, and the middle, or "logic" pin, that is connected to what will send the signal -- ie, one of the programmable data pins on the raspberry pi.

> ## Try this:
>
> Use pin 17 to control a transistor to power the LED from the blink.py program from the previous episode.
{: .challenge}

If you need more power than the transistor can handle, you can use the transistor to control a relay which works much the same way, but that has an electro-mechanical switch inside: you control the transistor that energizes a magnet which controls the switch.

If you're planning to work with power from the "mains" (i.e. wall electrical power), the simplest and safest way is to use a device expressly designed for that purpose. Here's an example of a device that can detect the change on a GPIO pin to turn electrical sockets on/off.

<a href="{{ page.root }}/fig/Power_Strip_MEDIUM.jpg">
  <img src="{{ page.root }}/fig/Power_Strip_FULL.jpg" alt="LED connected to GPIO 17" />
</a>

Devices like this carefully isolate the circuitry energized with the mains electricity. Don't try to work with high voltages directly without expert assistance.

{% include links.md %}
