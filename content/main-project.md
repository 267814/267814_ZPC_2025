---
title: "Handheld Gimbal"
date: 2021-12-18T11:10:36+08:00
draft: false
language: en
description: About Us
featured_image: /images/Tripod_scheme.jpg
---

# Introduction

***

---

___

The **3-Axis Camera Gimbal** is an advanced motorized stabilization system designed to address the challenge of shaky footage in handheld videography. Its primary purpose is to maintain a perfectly smooth and stable camera orientation by actively and automatically compensating for unwanted external movements, such as hand tremors or vibrations from walking.

At the core of this system is an **Inertial Measurement Unit *(IMU)***, which integrates a gyroscope and an accelerometer. This sensor package provides high-frequency, real-time data about the gimbal's current orientation in 3D space. This data is used to stabilize three independent axes of motion: pitch *(up/down tilt)*, roll *(side-to-side tilt)*, and yaw *(left/right rotation)*. The physical stabilization is achieved by three servo motors, with each motor precisely counteracting the detected motion on its respective axis.

The entire system is governed by an **Arduino Nano** controller, which functions as the central processing unit. The Arduino continuously reads orientation data from the IMU and executes a closed-loop feedback mechanism. It calculates the error between the current orientation and the desired stable orientation *(i.e., "level")*. To ensure the corrective movements are both rapid and precise without oscillating or overshooting, a Proportional-Integral-Derivative *(PID)* control algorithm is implemented. This project demonstrates a practical application of mechatronic principles, combining sensor technology, control theory, and mechanical design to create a functional stabilization prototype.
## Scheme

Here is a very simple scheme, that shows how will the gimbal works and look.

<p align="center">
  <img src="/images/" alt="Gimbal scheme" class="rounded-2xl shadow-lg" width="600">
</p>


# Assembly

***

---

___

## Handle

## Holder
## Arms
## 
## Controls

### Arduino
### Gyroscope
### Motors
### JoyStick
### Code

## Logo

# Prototype

***

---

___

# Final product

***

---

___
