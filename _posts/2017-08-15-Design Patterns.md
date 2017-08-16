---
layout: single
title: Design Patterns
author_profile: true
read_time: true
comments: true
share: true
related: true
---

Part of my work for an undergraduate thesis is to build an application based on graphlets. This application parses a file to generate a graph then uses the graph to create graphlet degree vectors (GDV) for each node. Once that initial step is completed it uses the GDVs to put together a matrix and perform other statistical analysis.

While writing this application I’ve run into design issues. Initially everything was just methods. I wrote it this way in order to ensure everything was working, at the time I didn’t realize how much extra work I was creating for myself. I’ve refactored all of the code once so I’m using objects and not repeating some code unnecessarily. However, now when I need to add features, like being able to process different types of graphs, (directed, weighted, signed, etc…) I’m having to rewrite base methods with more logic. This work it’s not a very efficient use of my time and overall it’s a bad practice. This is why I’ve picked up a textbook on design patterns.

Improving a current application I’m working on is one reason to study design patterns, another is to become a better programmer in general. Designing a program with efficiency, modularity, and reusability in mind is difficult. Modularity is a feature of object oriented programming that makes it great. If we strike a proper balance between specific and general when designing our system we can use our solution again when a similar problem arises.

Throughout a degree in Computer Science you learn many of the object oriented programming (OOP) tools like classes, interfaces, inheritance, diagrams for relationships and interaction, and many more. However, how all these tools can work together to achieve a simple and general solution isn’t a focus of the curriculum. This isn’t really because of any deficiency in the CS program, it’s more that there is so much material to cover in four years. When it comes to OOP specifically time has to be spent reinforcing the concepts. Being familiar with these concepts equips us to tackle something like design patterns when we’re ready or when we realize that we’re writing the same method for the 4th time and want to find a better way.

When picking up the textbook for the first time I skimmed through a few of the chapters and started to wonder if I’m ready to take on this topic. Some of the ideas were not clear to me right away and others never became clear. My assumption is that I will have to revisit this topic many times throughout my career. There are some videos on the Google sponsored YouTube channel about interviewing at Google. In the coding interview video it’s mentioned that if you have 5+ years of experience in the industry you could be asked system design questions. While I may not get the full benefit from this textbook at least now I will have a better idea of system design and maybe even improve my graphlet program.

So with that out of the way, what are design patterns? They are patterns that come up again and again when designing a system and have proven to be effective and reusable. (I was going to write simple but I’m not convinced of that yet). In a sense they capture the experience of those who have designed many systems. The textbook is organized as a catalogue of design patterns that can be used as a solution when a similar problem arises. Experienced programmers have noticed these patterns showing up again and again and have tested these solutions in production code.

Rather than getting into the specific details I will provide some real world examples, since design patterns occur everywhere. Consider construction, when building a structure like a bridge, house, or road the solution at the core of the problem is the same and is used over and over again. We can use the core solution many times and still not solve the problem the same way twice. Another example is found in storytelling. Most movies, books, and songs tell the same old stories over and over again but in very different ways.

That’s the general idea, or what I’ve been able to gather. I know I haven’t gone into much technical detail here but I find these abstractions useful before diving into something new. Next time I write about design patterns I will try to write a more concrete definition and give an example. I still think this general idea is fairly exciting and promises to improve your code at any level.
