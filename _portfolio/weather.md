---
title: "Weather App"
excerpt: "Get your current weather based on location"
header:
    teaser: weather-th1.png
sidebar:
  - title: "Role"
    image: weather-th2.png
    image_alt: http://placehold.it/350x250
    text: "Designer and Developer"
  - title: "Responsibilities"
    text: "Build webpage using HTML, CSS, Javascript and jQuery. Work with DarkSkies API"
---

[Demo](https://mdrakos.github.io/weather-app/)

[Source Code](https://github.com/MDrakos/weather-app)

This project is part of the progression on [FreeCodeCamp](http://www.freecodecamp.com).

Building this website helped me become more comfortable with jQuery and APIs.

When first visiting the site you will be asked to allow use of your location.
Once approved we show the coordinates and use a method to make a call to
the DarkSkies API.

With the data received, again in JSON format, we use other methods to get
summary, temperature, and icon information.

The icon information is interesting. There are a limited number of icon
values returned from the API and based on what value is returned we can
render and animated weather element using CSS. (Credit to Josh Bader
for his [wonderful icons](https://codepen.io/joshbader/pen/EjXgqr))

Finally, a button at the bottom represents the current units and clicking
it does a quick conversion to either celsius or fahrenheit.

This website furthered my exploration of jQuery and APIs.
