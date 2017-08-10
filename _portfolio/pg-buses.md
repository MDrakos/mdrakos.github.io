---
title: "PG-Buses"
excerpt: "A mobile app for the Prince George Transit System"
header:
    teaser: pg-buses-logo-th.png
sidebar:
  - title: "Role"
    image: pg-buses-logo.png
    image_alt: http://placehold.it/350x250
    text: "Developer"
  - title: "Responsibilities"
    text: "Data acquisition and updating. Schedule and map implementation. Task runner setup"
gallery:
  - url: pgbuses-intro.png
    image_path: pgbuses-intro.png
  - url: pgbuses-home-collapsed.png
    image_path: pgbuses-home-collapsed.png
  - url: pgbuses-home-expanded.png
    image_path: pgbuses-home-expanded.png
  - url: pgbuses-menu.png
    image_path: pgbuses-menu.png
  - url: pgbuses-routes.png
    image_path: pgbuses-routes.png
  - url: pgbuses-schedule.png
    image_path: pgbuses-schedule.png
  - url: pgbuses-find-stop-empty.png
    image_path: pgbuses-find-stop-empty.png
  - url: pgbuses-find-stop.png
    image_path: pgbuses-find-stop.png
  - url: pgbuses-map-full.png
    image_path: pgbuses-map-full.png
---

[App Download](http://tinyurl.com/app-pg-buses)

*Unfortunately the source code for this project is in a private
repository as there are plans to make improvements*

This project served as a way to explore mobile and web development while
building something useful for residents of our town. I was part of a team
that designed, developed, and deployed this app using the Agile methodology.

This app was developed over two courses. During the first course, I
helped develop the initial schedule and route pages. The initial course
was my introduction to many new technologies such as JavaScript, Ionic,
and Angular. Because of my, and my team members', unfamiliarity with
these technologies, development was slow. By the end of the first course
we have a usable product, however many ideas and plans were left out
in order to have a working prototype.

During the second course we were able to implement many more features.
My responsibilities also shifted at this time. I was tasked with sourcing
our data from PG Transit and making it usable for our purposes.

The transit data is received in a JSON format. We were initially working
with this data as it was received from PG Transit without any modification.
Since these JSON files are very large, and our app is really just a front
end, processing times caused the application to hang. For instance, when
we wanted to populate a map with all of the stops on a route the application
would eventually complete it's task on newer, more powerful, devices but
simply crash on older ones.

Unfortunately, no one in the group had been exposed to databases at the
time so a decision was made to continue using the JSON files rather than
try to implement new (to us) technology. This meant that we would have to make the
JSON files more manageable. I wrote a small Python program that would take
the JSON files and break them down into more manageable chunks that could
be processed more easily. Throughout development as other team members
worked on their contributions I would get requests to modify or generate
JSON files for them. I would also work with each team member to help them
implement their ideas using the data we had. This involved using Angular to
parse the JSON files and capture the correct information then present it
properly on the page. With the smaller files in place we were able to
add the functionality we wanted without long processing times.

The real test of my Python program came when PG Transit updated their
information for a new season. I was able to get the original JSON files,
run my program and import the new files without any conflicts. The next
step would be writing a service that listens for these changes, runs
the python program and pushes the new changes.

All of the information provided by the app about routes, schedules, and
stops come from this data set. After taking a course in databases I can
see how this app would have improved with one, as working with the JSON
files proved to be difficult in some cases.

Below is a gallery showing some of the pages that use the JSON data.

*Gallery*

{% include gallery caption="PG Buses Gallery" %}
