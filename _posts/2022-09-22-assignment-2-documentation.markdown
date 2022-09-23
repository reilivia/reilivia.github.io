---
layout: post
title:  "Assignment 2 Documentation"
date:   2022-09-23
categories: creative coding
---

## Plan for Assignment 2
For assignment 2, I have to stick with p5.js. At first I want to use Canvas API in javascript and move on from p5.js. However, I spent too much time figuring how to use canvas API to create recursion. In the end, I am back to p5.js for this assignment.

## Documentation

<div align ="center">
  <iframe width="576" height="366" src="https://editor.p5js.org/reilivia/full/z7X-I0J8Z"></iframe>
</div>
<br>

Note: The embeded code is a smaller screen version. Click here to see the [FullScreen Version][assignment2-fullscreen].

In general, there are three (3) main design choices for my Assignment 2 design. 
1. [Mouse Interaction][mouse-interaction]
2. [Recursive Rectangle][recursive-rectangle]
3. [Audio Button][audio-button]

In this blog post, I will explain my idea and how I incorporate each one of them into one single piece of work. 

# Mouse Interaction

There are two mouse interaction, the mouse trail and mouse ripple.

Mouse trail is an array of circles that follow the mouse. The circles is white and positioned at the bottem after the background. The idea is this mouse trail acts like a flashlight so you can see what is happening on the screen. The mouse trail start of with a certain size, and gradually scale down and dissapear and new circle appears.

Mouse ripple is a group of three circles. When you click on the canvas, it will create three circle that start with size 0, and gradually scale up until it covers the whole canvas.

# Recursive Rectangle
In assignment 2, I use the recursive function on a rectangle. It might look simple at first, however after adding some random weight stroke and rotation on the rectangle, it created this spiral illusion.

The rectangles are black, the same colour as the background. You can only see it through the mouse trail, the mouse ripple and audio button.

# Audio Button
In the middle of the canvas, there is a dark grey button. You can see the recursive rectangles on this button more clearly if you hover over the button. The idea is to make the button act as a window. You can peek on the recursive rectangle movement.

Other than mirror, this button works as a button to play/stop music. The music I choose is called "Muriel" by Bobby Richards. In addition to that, if you click on anypart of the screan, it will play a bell sound to accompany the ripple effect. This way you can jam on the music and interact with it. 


[assignment2-fullscreen]: https://editor.p5js.org/reilivia/full/e7vwtiFS2

[mouse-interaction]: https://reilivia.github.io/creative/coding/2022/08/21/exploring-the-mouse-interaction-array.html
[recursive-rectangle]: https://reilivia.github.io/creative/coding/2022/08/21/exploring-the-recursion-function.html
[audio-button]: https://reilivia.github.io/creative/coding/2022/08/21/creating-the-audio-button.html

