---
title: "Permissions"
teaching: 20
exercises: 0
questions:
- "What Unix permissions are needed to interact with the GPIO?"
- "How should permissions be structured for production versus development?"
objectives:
- "Inspect "
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---
The interface between the hardware and software of the Raspberry Pi is the linux kernel. The kernel builds a [file system located at /sys](https://man7.org/linux/man-pages/man5/sysfs.5.html) that includes entries that represent all of the physical hardware that the kernel "knows" about. The entries for the GPIO are in /sys/class/gpio.

In early versions of Raspbian, the GPIO could only be accessed by root initially and a series of steps were necessary to assign the GPIO devices permissions that allowed ordinary users to access them. With newer versions of Raspbian, this is not necessary. By default the GPIO devices can be controlled by anyone in the "gpio" unix group. If you have problems with permissions, check to make sure you're in the gpio group and add your account to the group if necessary.

Group memberships appear in /etc/group and you can use grep to do pattern matching:
~~~
$ grep gpio /etc/group
~~~
{: .language-bash}

~~~
gpio:x:997:pi
~~~
{: .output}

The first field is the name of the group and the last field can be a comma-delimited list of usernames that are in the group.

There are a number of other groups that might be relevant to any particular project you want to work on. As long as you're using the "pi" account, you should already be in all of the important groups:

~~~
$ grep pi /etc/group
~~~
{: .language-bash}

~~~
adm:x:4:pi
dialout:x:20:pi
cdrom:x:24:pi
sudo:x:27:pi
audio:x:29:pi
video:x:44:pi
plugdev:x:46:pi
games:x:60:pi
users:x:100:pi
input:x:105:pi
netdev:x:109:pi
pi:x:1000:
spi:x:999:pi
i2c:x:998:pi
gpio:x:997:pi
~~~
{: .output}

For development purposes, using the "pi" account is convenient. For security purposes, a finished device would use an alternate username and put that account only in the groups necessary for it to accomplish its tasks. You can change group memberships by editing the file. Or you can add a username to a group using the command below.

~~~
$ sudo usermod -a -G groupname username
~~~
{: .language-bash}

{% include links.md %}
