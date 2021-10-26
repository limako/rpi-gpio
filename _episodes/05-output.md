---
title: "Using GPIO Pins for Output"
teaching: 20
exercises: 0
questions:
- "How can you use pins to control things?"
objectives:
- "Learn how to control digital pins via python."
keypoints:
- "You can signal with digital pins."
- "Don't try to power things with digital pins."
---
If you can turn a digital pin, you can use that as a signal to turn on other devices. If you're planning to work with power from the "mains" (i.e. wall electrical power), the simplest and safest way is to use a device expressly designed for that purpose. Here's an example of a device that can detect the change on a GPIO pin to turn electrical sockets on/off.

<a href="{{ page.root }}/fig/Power_Strip_MEDIUM.jpg">
  <img src="{{ page.root }}/fig/Power_Strip_FULL.jpg" alt="LED connected to GPIO 17" />
</a>

Devices like this carefully isolate the circuitry energized with the mains electricity. Don't try to work with high voltages directly without expert assistance.

For low power devices, like small stepper motors or servos, you can use a relay to use an electrical signal to open or close a switch to a power source.



{% include links.md %}
