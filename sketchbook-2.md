---
layout: default
title: "Digital Sketchbook 2"
permalink: /sketchbook-2/
---
Sketchbook 2
============

Pixels to points: Technical exploits on the path to pen plotting
----------------------------------------------------------------

Juggling data is usually no fun. While taking CS35 at Harvey Mudd last year got me excited about many computer-sciency things, the weekly drudgery of getting useable data informed me that data analytics likely (or, hopefully) plays no major role in my future. 

But it's a crucial skill nonetheless. And to proceed with my pen plotter project, I would need to take the data from my custom fractal Processing sketch and export it in a format that would play nicely with other pieces of software. I dragged my feet on this for a while - I thought it was going to be much more difficult and time-consuming than it ended up being. As I am reminded again and again, all I needed to do was take the plunge.

Why? What exactly?
------------------

Before now, every fractal imaged I've included in my sketchbook has been, essentially, a glorified screenshot: an array of the pixels as they were displayed in the window on my screen. What I needed was the **path** - the data that actually defines the fractal's structure, rather than a mere pixillated representation. This meant I needed to get the data in a *vector* format, rather than a *raster* one.

You can think of this difference like that between a picture of an artwork and the work itself - the difference between seeing something through a grimy window versus holding it in your hand.

This vector format will make it possible for the 3D printer to retrace the exact path of the fractal and draw it on the paper; I am referring to [this guide](https://www.youtube.com/watch?v=CuWZWAfBsm8) to get the software set up.

How I did it
------------




![title](/images/Sketchbook 2/####.jpg)
