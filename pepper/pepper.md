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

## Sleep Mode

Pepper does not always need to be active, but as the boot process can take longer it can sometimes be advisable to put pepper to sleep.
To put pepper to sleep mode autonomous life must be active.

Simply lay your hand on pepper head covering all three of the tactile sensors and the palm covering the top camera.
Holding your hand there for three seconds puts pepper to sleep.
Pepper will make sounds when holding your hand in this position of:
"blop", "blop", "click".
The eyes and status LEDs will then turn purple for a short moment signalling that pepper is now in sleep mode.

To wake pepper up, simply touch the tactile sensor in pepper head.
Pepper will then wake up and enter the standing pose. 

## Powering off Pepper

To turn off pepper it is the same process as turning on pepper.
It is recommended to put a hand on its back to keep it in position whilst you turn pepper off.

Press and hold the chest button for three seconds until pepper says `"GNUK GNUK"`.
Pepper will then begin the shutdown sequence and will be fully turned off when all the LEDs have gone dark.

## Emergency turn off

Pepper can also be turned off in an emergency, this is not recommended in general use.
This process can be done by pressing and holding the chest button for eight seconds. 
Ensure that pepper is in a safe position when doing this so that the robot does not fall and damage components.

The chest button will turn green and pepper will follow by saying `"GNUK GNUK"`.
The LED lights should then fade quickly.

## Emergency Stop

As with all robotic systems, an emergency stop button is pivotal for the safety of the robot and its environment.
Pepper is no different however turning off pepper using the emergency stop is not recommended in normal use.

If pepper does need to be turned off in an emergency, then press the stop button through the soft cover at the base of the neck.

When pepper is off, the chest button will not activate until the stop button has been unlocked.
To unlock the stop button, lift the soft cover and then turn the stop button clockwise until it snaps back in the up position.
Afterwards be sure to close the soft cover being careful not to press the stop button.