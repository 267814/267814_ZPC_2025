---
title: "Electronic system"
date: 2021-12-18T11:10:36+08:00
draft: false
language: en
featured_image: ../assets/images/featured/featured-img-placeholder.png
summary: Here we were learning how to use and code Arduino and various components for it. For example buttons, LED diodes, potenciometrs etc.
description: Here we were learning how to use and code Arduino and various components for it. For example buttons, LED diodes, potenciometrs etc.
author:
authorimage:
categories: Blog
tags: ["Mini-project"]
---

# Intro

***

---

___

This section shows a project I built using Arduino and the Tinkercad simulator. My goal wasn't just to connect a few wires, but to build an interactive controller that has advanced feedback. I programmed it to use timers and logic to watch for "critical" situations, kind of like a safety system you'd find in a real machine.

## Circuit 

***

---

___

Here’s how the circuit works. The Arduino Uno is the brain for everything. I use a potentiometer (the black knob) as the main input. The Arduino reads the position of the knob and does two things at once:

1. It tells the servo motor to turn to that exact same angle.

2. It lights up the LEDs to show what "zone" you're in. First just green, then green and amber, and finally all three including the red.

A key part of the design is the external battery pack. The servo motor needs more power than the Arduino can safely provide, so I gave it its own battery. I then had to connect the "ground" (GND) from the Arduino to the battery's ground. This is an essential step to make sure all the parts can "talk" to each other correctly.

<p align="center">
  <img src="/images/Obvod.png" alt="Tripod scheme" class="rounded-2xl shadow-lg" width="700">
</p>

## Real-World Application

***

---

___

As the video shows, this isn't just a random toy. It's a prototype for a real-world control system, like a control panel for an industrial motor or a furnace.

+ The Potentiometer: This is the main dial the operator uses to set the power level or temperature.

+ The Servo: This represents the actual motor or valve that's doing the physical work (like opening a fuel line or spinning a mixer).

+ The LEDs: These are the status lights showing the load. Green means "Idle," amber means "Working Load," and red means you're "redlining" at maximum power.

The most important feature is the 3-second safety timer. I programmed the Arduino to watch how long the system is in the red zone. If the operator pushes the system to its limit and leaves it there for more than 3 seconds, the red LED starts flashing. This is a serious alarm telling the operator, "EMERGENCY! Reduce the load now before something overheats or breaks!"

<div class="max-w-xl mx-auto mb-8">
  <video 
    src="/images/Funkce obvodu.mp4" 
    class="w-full h-auto rounded-2xl shadow-lg"
    autoplay
    loop
    muted
    playsinline>
      </video>
</div>