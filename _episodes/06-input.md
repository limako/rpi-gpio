---
title: "Permissions"
teaching: 0
exercises: 0
questions:
- "Key question (FIXME)"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---
In early versions of Raspbian, the GPIO could only be accessed by root initially and a series of steps were necessary to assign the GPIO devices permissions that allowed ordinary users to access them. With newer versions of Raspbian, this is not necessary. By default the GPIO devices can be controlled by anyone in the "gpio" unix group. If you have problems, check to make sure you're in the gpio group and add your account to the group if necessary.

{% include links.md %}
