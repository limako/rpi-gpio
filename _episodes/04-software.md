---
title: "GPIO via Bash"
teaching: 0
exercises: 0
questions:
- "How "
- "What do pins do?"
- "How can you refer to pins?"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---
It is possible to access the GPIO directly via the command line using bash commands to configure and manipulate the devices directly via the linux kernel.

This command will make the pin available to userspace for programming:
~~~
$ echo "17" > /sys/class/gpio/export
~~~
{: .language-bash}

This command will set whether the pin should be for input or output:
~~~
$ echo "out" > /sys/class/gpio/gpio17/direction
~~~
{: .language-bash}

This command will set the pin to "HIGH."
~~~
$ echo "1" > /sys/class/gpio/gpio17/value
~~~
{: .language-bash}

And this sets it back to "LOW."
~~~
$ echo "0" > /sys/class/gpio/gpio17/value
~~~
{: .language-bash}

And this sets it back to "LOW."
~~~
$ echo "17" > /sys/class/gpio/unexport
~~~
{: .language-bash}

The capabilities are limited, however, and not all of the functionality is available using these low-level tools. There is more [complete documentation](https://www.kernel.org/doc/Documentation/gpio/sysfs.txt)

There are 

WARNING! raspi-gpio set writes directly to the GPIO control registers
ignoring whatever else may be using them (such as Linux drivers) -
it is designed as a debug tool, only use it if you know what you
are doing and at your own risk!

The raspi-gpio tool was designed to help hack/debug BCM283x GPIO.
Running raspi-gpio with the help argument prints this help.
raspi-gpio can get and print the state of a GPIO (or all GPIOs)
and can be used to set the function, pulls and value of a GPIO.
raspi-gpio must be run as root.


{% include links.md %}
