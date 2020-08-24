---
title: "Introduction"
teaching: 10
exercises: 0
questions:
- "How can Raspberry Pi interact with other devices?"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "Raspberry Pi supports many means of connecting to other devices."
- "The GPIO offers digital pins that can be configured for many purposes."
- "The Raspberry Pi does not have analog pins like an Arduino."
---

The Raspberry Pi comes with a large array of connectors to interact with other devices. Some of these are tied to very specific forms of input/output (think ethernet, usb, hdmi, camera, etc.) Along one side of the board, however, is a set of pins that are available for "general purpose input/output" or GPIO.

Some of these have specific purposes. Four provide power (two at 3.3v and two at 5v).  Eight are "ground" connections to complete a circuit from any of the other pins. Some are pre-configured to be used for several kinds of serial connections (i.e. UART, SPI, & I2C). With raspi-config, you can configure the Pi to turn on this functionality.

The other pins are undefined and can be easily used for either input or output. In both cases, these are boolean (true or false) operations. For input, they can detect HIGH or LOW and for output, they can be set to be HIGH or LOW.

> ## Important:
>
> When a GPIO pin is set HIGH, it provides enough power to be detected, but isn't designed to actually power much more than an LED. If you connect a device that draws too much power, its possible to damage the circuitry of the Raspberry Pi. Be cautious and make sure to use resistors to ensure the safety of your Pi.
{: .callout}

This means that the Raspberry Pi has no "analog" pins, like the Arduino. The GPIO can be used to detect on/off events, like switches. Or receive data via a serial connection. But to convert a voltage into a digital signal, you need to use another device, like an Analog-to-Digital converter. Or an Arduino.

{% include links.md %}
