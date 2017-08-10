---
title: "JavaScript Calculator"
excerpt: "Attempt to clone the iPhone calculator"
header:
    teaser: calc.png
sidebar:
  - title: "Role"
    image: calc.png
    image_alt: http://placehold.it/350x250
    text: "Designer and Developer"
  - title: "Responsibilities"
    text: "Design and development"
---

[Demo](https://mdrakos.github.io/JSCalculator/)

[Source Code](https://github.com/MDrakos/JSCalculator)

This project was a great opportunity to further my exploration of
jQuery. Throughout the project I used jQuery extensively to manipulate
DOM objects.

Each button has a unique value associated with it that is read whenever
a button is pushed. Depending on the value received, which is checked
via a regex, program control flows to either executing an operator or
a special function.

Each button push is captured and used via a stack. Every button is pushed
onto the stack and popped off as necessary. For instance when entering
5+5:

- 5 is not an operator or special button so it is simply pushed onto
the stack and left there.
- \+ is an operator, however we do not need to use this value until we have
at least one more argument and we push equals.
- 5 is the same as the first step
- Finally, when we push equals we pop the necessary arguments and operator
off of the stack and store them. Depending on the operator we call the
appropriate method and push the answer onto the now empty stack. During
this time the display and display history are updated as well.

Overall this is a fairly simple implementation however I ran into various
edge cases that I'm still attempting to fix. Pushing multiple operators
or special characters throws an error. Negating a number before it is entered
also causes the answer to be NaN. There are a few other edge cases I'm
aware of and that I'm attempting to fix.

As I experiment more with jQuery I'm becoming comfortable with it's basic
functionality. This project was challenging in a different way than the
previous ones. To implement the calculator I had to think more of the program
as a whole and how to design it. Eventually, I would like to go over the
JavaScript again and clean up the design.