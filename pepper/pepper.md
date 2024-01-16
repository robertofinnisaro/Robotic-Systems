---
title: "Beginners guide to Pepper"
date: 2024-01-16T20:00:00-00:00
draft: false
cover:
    image: img/pepper.jpg
    alt: "Pepper Robot"
    caption: "Pepper Robot"
    hidden: true
    hiddenInSingle: true
summary: "\"This is a beginners guide to setting up Pepper.\""
tags: ["ROS", "Pepper", "Robotics"]
---

## Pepper Start Up

To start up pepper, first make sure that pepper is in an open environment and on a flat surface.
On boot, pepper will check its surrounding area to ensure that the area that around it is safe to operate in.

To initiate peppers boot sequence, press the chest button once.

The LEDs on pepper will then begin to start blinking and fading which shows where pepper is up to in the boot sequence.
The boot process is completed when pepper says `"OGNAK GNOUK"`.

Pepper is now booted and applications can be run either automatically or interactively now.

## Autonomous Life

One of the most important features of pepper is autonomous life. 
These gives pepper the functionality of being alive and responsive. 

In the boot sequence you will have seen pepper scan the surrounding area.
After this pepper orientates their head towards a human ready to be interacted with.

To toggle the state of autonomous life, simply press the chest button twice.

When the state changes from `off -> on`:
- Pepper makes a happy grunt.
- Turns on the motor stiffness.
- Move into a standing posture.
- Resumes its life.

When the state changes from `on -> off`:
- Pepper sighs.
- Stops all activities.
- Moves into the resting posture.
- Turns off the motor stiffness.