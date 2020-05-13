---
layout: default
title: "Digital Sketchbook 2"
permalink: /sketchbook-2/
---
Sketchbook 2
============

Pixels to paths: Technical exploits on the journey to pen plotting
------------------------------------------------------------------

Juggling data is usually no fun. While taking CS35 at Harvey Mudd last year got me excited about many computer-sciency things, the weekly drudgery of getting useable data informed me that data analytics likely (or, hopefully) plays no major role in my future. 

But it's a crucial skill nonetheless. And to proceed with my pen plotter project, I would need to take the data from my custom fractal Processing sketch and export it in a format that would play nicely with other pieces of software. I dragged my feet on this for a while - I thought it was going to be much more difficult and time-consuming than it ended up being. As I am reminded again and again, all I needed to do was take the plunge.

Why? What exactly?
------------------

Before now, every fractal imaged I've included in my sketchbook has been, essentially, a glorified screenshot: an array of the pixels as they were displayed in the window on my screen. What I needed was the **path** - the data that actually defines the fractal's structure, rather than a mere pixillated representation. This meant I needed to get the data in a *vector* format, rather than a *raster* one.

You can think of this difference like that between a picture of an artwork and the work itself - the difference between seeing something through a grimy window versus holding it in your hand.

This vector format will make it possible for the 3D printer to retrace the exact path of the fractal and draw it on the paper; I am referring to [this guide](https://www.youtube.com/watch?v=CuWZWAfBsm8) to get the software set up.

How I did it
------------

SVG is the current filetype standard for all things vector, thanks to some advantages: it's a very flexible format and it uses XML, so humans can read and (mostly) understand its files if opened in a test editor. Simple files can thus be shockingly simple; as I learned on the [W3Schools tutorial page](https://www.w3schools.com/graphics/svg_polyline.asp), all I need for a polyline are a few tags, some basic setup and style info, and my list of points:

    <svg height="1000" width="1800">
        <polyline points="550.0,200.0 424.508,239.796 444.643,369.898 464.778,500.0 596.429,500.0 616.563,630.102 748.214,630.102 879.865,630.102 900.0,500.0 920.135,630.102 1051.786,630.102 1183.437,630.102 1203.571,500.0 1335.222,500.0 1355.357,369.898 1375.492,239.796 1250.0,200.0"
        style="fill:none;stroke:black;stroke-width:1" />
    </svg>

I then realized: since my fractal program works recursively, it actually draws out the lines in the exact order that a pen plotter would. Yay! That meant I simply need to push them to a global list, check for duplicates, and finally accumulate them to a long string that I write to disk as a text file with the proper boilerplate & formatting and a .svg file extension. Simple! 

The above code defines the following fractal, shown in its native Processing at left and then opened with Inkscape at right:

![Processing at left and Inkscape path at right](/images/Sketchbook 2/SimpleCompare.jpg)

A simple "Object to Path" operation within Inkscape takes the barebones polyline object and adds its more complex Inkscape flavoring with no work on my part. Sweet! I thus get a path with nodes I can control just like any native path. That makes it possible to integrate with the plugins I'll exploit to get my printer plotting. Now on to that!

Bonus
-----

Getting my fractals into Inkscape opens a whole jar of possibilities, and I wish I had gone about this sooner. Fractals that once went off the screen in Processing are now manipulable in all their glory: monstrous clusters of control points and all...

![Zoomed out at left and zommed in at right](/images/Sketchbook 2/ComplexCompare.jpg)
