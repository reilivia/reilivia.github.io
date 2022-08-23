---
layout: post
title:  "Assignment 1 Documentation"
date:   2022-08-21
categories: creative coding
---

## Initial Idea
In the beginning, I wanted to create an underwater theme for my design. The reason for this is because i was inspired by the [Noise Wave][noise-wave] example. Going from there, I wanted to match the underwater theme and add bubbles to float around on the canvas. This idea came up after I learn about the bouncing square in creative coding class.

<div align ="center">
  <iframe width="576" height="366" src="https://editor.p5js.org/reilivia/full/v-ln9OeoB"></iframe>
</div>
<br>


## Documentation

In general, there are three (3) main design choices for my assignment 1 design. I have done some research and experiment on each one of the topic related on each section. Check out the details on the link down bellow:
1. [Noise Wave Background][Noise-Wave-Background]
2. [Bubbles Class][Bubbles-Class]
3. [Change Colour][Change-Colour]

When combining all three of them, I had to create four custom function. I did this because i want to catagorized each sections and have a neat code.
{% highlight ruby %}
  noiseWave()
  addBubbles()
  changeColour() 
  textContent()
{% endhighlight %}

Iside from that, I created a variable for colours. This will make it easier for me later on when I edit the colour changing function.
{% highlight ruby %}
  var backgroundColour = "#000054"
  var waveColour = "waveColour"
  var bubbleColour = "bubbleColour"
{% endhighlight %}

## Iteration of Initial Ideas

After learning more about each topic, I was able to tweak my original code and create a design with a sci-fi theme. Compare to the first design, here are some things that I changed:
* The `fonts` of the text
* The `Bubble` (changed the shape, the size, the speed, the movement direction)
* The `noiseWave()` (increase the fluidity and speed and added 2 more vertex)
* The `changeColour()` (changed the colours into a brighter and vivid colours)

<div align ="center">
  <iframe width="576" height="366" src="https://editor.p5js.org/reilivia/full/hpL8-SsKA"></iframe>
</div>
<br>


[noise-wave]: https://p5js.org/examples/math-noise-wave.html

[Noise-Wave-Background]:https://reilivia.github.io/creative/coding/2022/08/18/exploring-the-noise-wave.html
[Bubbles-Class]:https://reilivia.github.io/creative/coding/2022/08/19/creating-a-bubble-class.html
[Change-Colour]:https://reilivia.github.io/creative/coding/2022/08/20/change-colour-on-mouse-over.html