---
title: "roboMaus"
excerpt: "3D printed robotic tank"
header:
    teaser: roboMaus-teaser.png
sidebar:
  - title: "Role"
    image: roboMaus-teaser.png
    image_alt: http://placehold.it/350x250
    text: "Designer and Developer"
  - title: "Responsibilities"
    text: "Logical Design. Drivers, data structures, and concurrency"
gallery:
  - url: sam4s.png
    image_path: sam4s.png
  - url: oled.png
    image_path: oled.png
  - url: hbridge.png
    image_path: hbridge.png
  - url: hall-sensor.png
    image_path: hall-sensor.png
  - url: motor.png
    image_path: motor.png
  - url: treads.png
    image_path: treads.png
  - url: chassisv1.png
    image_path: chassisv1.png
    alt: "placeholder image 1"
  - url: chassisv2.png
    image_path: chassisv2.png
    alt: "placeholder image 2"
  - url: chassisv3.png
    image_path: chassisv3.png
    alt: "placeholder image 3"
---

[Source Code](https://github.com/MDrakos/RoboMAUS)

The roboMaus project was used to explore hardware programming,
data structures, and concurrency.

The idea was to see if independent treads of a tank could be controlled
via software rather than a gear system. In order to implement and test
this idea our team had to develop hardware drivers for each physical
component, software to populate data structures with path information and
facilitate communication amongst the hardware components.

### Hardware
The main hardware used for this project:

*SAM4SD32 Microcontroller*

<img src="/images/sam4s.png" height="250" width="300">

- This is the brain of the project.
- Code is flashed and stored on the ROM
- Extension pins allow for connection to all other hardware components


*ATMEL OLED1 Xplained Pro*

<img src="/images/oled.png" height="250" width="300">

- Used to initialize the program via a button push
- Display statistics (number of rotations) on OLED display


*L298 H-Bridge Dual Bidirectional Motor Driver*

<img src="/images/hbridge.png" height="250" width="300">

- Allows for bidirectional independent control of two electric motors
- Track and wheel kit

*Hall effect sensors*

<img src="/images/hall-sensor.png" height="250" width="300">

- Used to measure distance by counting wheel rotations

*Motors*

<img src="/images/motor.png" height="250" width="300">

*Treads*

<img src="/images/treads.png" height="250" width="300">

*Battery Pack*
- For power

The chassis was an opportunity to explore 3D printing. Two prototypes were
developed before the final chassis.

*Chassis Version 1*

<img src="/images/chassisv1.png" height="350" width="500">

*Chassis Version 2*

<img src="/images/chassisv2.png" height="350" width="500">

*Final Chassis*

<img src="/images/chassisv3.png" height="350" width="500">

Theses were all printed using a [Tinkerine DittoPro 3D Printer](https://store.tinkerine.com/products/ditto-pro)

### Data Structures
Each tread is controlled independently. Instructions for are stored in
two separate stacks for each tread as a 'tick' value. These values represent
the number of ticks we want to receive from a hall effect sensor.

A path is populated into each stack via 'tick' instructions. As instructions
are popped off the stack they are sent to the tread drivers which then sends the instruction
to the tread. Once feedback that the instruction was executed is
received from the hall effect sensors, the next instruction is popped off until
no instructions remain.


### Concurrency
Each hall effect sensor is connected to independent GPIO pins. This means
that the signals are being sent at the same time. To compensate for this
we implemented a pseudo-concurrent solution using boolean values. Each
sensor has a boolean value associated with it to determine if it should
still count 'ticks' or not. Unless both of the boolean values tell the
program to stop counting, we prevent the next instruction from being
popped off the instruction stack.

While not a true concurrent solution, we found it to work within our
expectations. Each boolean value is being updated concurrently and this
solution solved our problem without having to attempt implementing a
monitor, semaphore, or other complex concurrent solution in C.

### Challenges
Working with hardware was more difficult than anyone on our team imagined
it would be. Countless hours were spent consulting documentation, making
wires, testing voltages, and rewriting driver software.

This project was also my first experience with the C programming language.
Coming from Java this was difficult at first to pick up and I spent a
long time getting comfortable.

### Future improvements
Originally, we had planned to experiment how different data structures
affected performance however due to time constraints we were limited to
only using a stack though various other data structures were on our list.

{% include gallery caption="roboMaus Gallery" %}