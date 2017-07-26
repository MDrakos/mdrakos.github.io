---
title: "Wireless Trickle Network"
excerpt: "A wireless trickle network implemented on the SAM4S microcontroller using xbee wireless radios"
header:
    teaser: xbee.png
sidebar:
  - title: "Role"
    image: xbee-ant.png
    image_alt: http://placehold.it/350x250
    text: "Developer"
  - title: "Responsibilities"
    text: "Implement trickle algorithm, troubleshoot wireless communication"
gallery:
  - url: sam4s.png
    image_path: sam4s.png
  - url: oled.png
    image_path: oled.png
  - url: xbee-ant.png
    image_path: xbee-ant.png
  - url: xbee.png
    image_path: xbee.png
---

[Source Code](https://github.com/MDrakos/trickleNetwork)

[Video Demo (excuse the cheesy music and sound effects)](https://www.youtube.com/watch?v=FVWkvPiDZ3Y&feature=youtu.be)

The objective of this project was to use a series of SAM4S microcontrollers
with Xbee wireless radios attached to each to act as nodes in a wireless
communication network.

Each node, except for the 'seed' node, begins in a state of simply
listening for a signal from a specific node. When that signal is
received it maintains it's listening state, but also transmits a signal
of its own to another specific node. This propagates throughout the
network until each node is both receiving and sending. If the
communication chain is broken all nodes after where the break occurs
stop sending until a signal is again received at the break.

The seed node begins in an inactive state and is primed via a button
push. Once instigated the seed node will continuously send information
to the next node in line until it is told to stop.


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

*Xbee Wireless Radio*

<img src="/images/xbee-ant.png" height="250" width="300">

- Xbee RF modules for easy deployment and connectivity
- Configured using XCTU software
- Configured so each module would accept packets from a specific broadcast address

### Implementation
Once a packet was received from the correct node the one of the LEDs on
the SAM4S was set to blink. The blink timing depended on the RSSI signal
strength received from the sending node. The closer the node, the faster
the blink. Similarly, the OLED screen on the Xplained Pro extension was
configured to display the actual RSSI value, though this proved to be
inconsistent.

### Challenges
Troubleshooting wireless communication proved to be difficult. In some
cases a signal would be received when no signal was sent and, more commonly,
a signal sent with no acknowledgement of being received. Trying to track
down and pin point what was causing this errors simply came down to
trial and error in many cases.

We were not able to solve why our OLED display gave us strange and
inconsistent RSSI values. These discrepancies could have been from a
wireless communication error or a bug in our code that we weren't able
to track down.

An issue arose with our wiring for connecting the Xbees to the SAM4S.
The wires we manufactured worked, however they were the wrong size for
the extensions on the SAM4S, this led to some wires contacting each
other, which caused odd behaviour. After troubleshooting wireless
communication issues a decision was made to manufacture new wires for
the nodes that were giving us trouble, this time ensuring proper shielding
on the end connections.

### Thanks
A huge part of this project is built on top of MiniOS, an operating system
built for the SAM4S micro controller by [Rafael Roman Otero](http://embedntks.com/author/romanot/)

*Gallery*

{% include gallery caption="Trickle Network Gallery" %}