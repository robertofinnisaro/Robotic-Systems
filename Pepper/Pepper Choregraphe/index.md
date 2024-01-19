---
title: "Pepper Introduction with Choregraphe"
date: 2024-01-16T20:00:00-00:00
draft: false
cover:
    image: img/pepper-choregraphe.jpg
    alt: "Pepper and Choregraphe"
    caption: "Pepper and Choregraphe "
    hidden: true
    hiddenInSingle: true
summary: "\"This is a quick start to a first project with Pepper and Choregraphe.\""
tags: ["Choregraphe", "Pepper", "Robotics"]
---

## Introduction
This is a tutorial on how to create an open day style program for Pepper using Choregraphe. Pepper has unique capabilities that make it an ideal companion for events such as a University Open Day. It provides an interactive and memorable experience for visitors. In this tutorial, we will guide you through the process of creating dynamic behaviour that showcases some of Pepper's features and functions, how to make it interact with attendees and how it can leave a lasting impression on visitors.

## Prerequisites
Before getting started, there are some prerequisites that need to be completed. To accomplish this, ensure that you have the following:

1. A Pepper robot with Choregraphe software installed.
2. A basic familiarity with the Choregraphe interface.
3. A basic understanding on how Pepper operates and general knowledge on how to use Pepper safely.

## Open Choregraphe
The first step is to open Choregraphe, for this find and locate the application and launch it.
After the application has been opened, connect to your Pepper by entering the IP address.
To find the IP address, press the chest button on Pepper once and it will announce the IP address.

## Create a New Project
Once Pepper has been connected, the next step is to create a new project for your open day project.
For this, go to `File` > `New Project`.

Name your project with a suitable name: i.e `OpenDay` and choose a suitable location for the project to be saved in.

## Design the Open Day program
### Welcome Interaction
In the `Box Libraries` find the predefined `Animated Say` block located in `Speech` > `Creation` > `Animated Say`.

Double click on the box to edit some of the functionality. It is recommended to turn the speech speed down to 90%. This is also where you can enter a friendly welcome message to greet the visitors. 

You could implement a `Say` box here but `Animated Say` builds a more engaging welcome.

### Entertainment
Pepper has a built in tablet that can be used to for interaction. On of the interactions that can be used is displaying mp4 files. 

To use the tablet, find the `Show Image` box located in `Multimedia` > `Tablet` > `Show Image`. 

One of the videos that can be used in this section is an OpenDay video from your marketing team, download the video and place it in your project files and it will be able to be referenced through to the `Show Image` box. 

This feature can be integrated with `Animated Say` to better entertain visitors.

### Q&A Session
Implementation of a `Dialog` box found in `Speech` > `Creation` > `Dialog`, this can be used to respond to some common questions that visitors may be asking. In a future tutorial, we will look into integrating this with a database providing more detailed information about courses and the campus to visitors.

With this implementation, it is possible to use speech recognition to understand and answer visitor queries.

## Connect Boxes
In order for Choregraphe to understand any of the boxes they have to be connected to each other. To start connect the output arrows of each box to create a flow of interactions.

Ensure that there are smooth transitions between different behaviours.

## Compile and Install
To run the program on Pepper first the program needs to be complied, for this hit the compile button in the tool bar to build your Choregraphe project.

After the project has been complied, you can then install the compiled behaviour onto Pepper.

## Test Program
To test that the program works, first run the program on Pepper.
Then ensure that you run through all of the interactions that you programmed to see what all of the behaviours do.

During this process, you can make adjustments as needed to enhance the user experience with Pepper.

## Conclusion
After this tutorial, you should have successfully created an open day program for Pepper using Choregraphe. This is an ever evolving process that can be customised for events based on specific goals and features that you wish to completed depending on the event.