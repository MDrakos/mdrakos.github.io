---
title: "Wikipedia Viewer"
excerpt: "Get a random article or search Wikipedia"
header:
    teaser: wiki-th.png
sidebar:
  - title: "Role"
    image: wiki-th.png
    image_alt: http://placehold.it/350x250
    text: "Designer and Developer"
  - title: "Responsibilities"
    text: "Build webpage using HTML, CSS, Javascript and jQuery. Work with Wikipedia API"
---

[Demo](https://mdrakos.github.io/wikipedia-viewer/)

[Source Code](https://github.com/MDrakos/wikipedia-viewer)

This project is part of the progression on [FreeCodeCamp](http://www.freecodecamp.com).

Building this website helped me become more comfortable with jQuery.

The use of jQuery in this website is fairly straightforward. Most of the
heavy lifting is done by the search function which is called when the enter
key is pressed (via keycode=13).

```
$('#search').keyup(function (e) {
   if (e.which === 13) {
     search();
   } ...
```

At this point we make an ajax call to the Wikipedia API and append
whatever was typed in the search bar. The data we receive back is in
the JSON format and we store that in an array.

Finally we loop through the results array and append well elements for
each result we have received via jQuery.

The source code itself is fairly small. Check it out in the link above.

Everytime you build a new website your skills in HTML, CSS, and JS improve.
This project also gave me an opportunity to explor jQuery and APIs a little
more.
