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
  <iframe width="750" height="500" src="http://digitalmedia.rmit.edu.au/~s3862934/creativecoding_assignment2/"></iframe>
</div>
Note: Click here to see the [FullScreen Version][assignment2-fullscreen].
<br>

In general, there are four (4) main design choices for my Assignment 2 design. 
1. [Mouse Interaction][mouse-interaction]
2. [Recursive Rectangle][recursive-rectangle]
3. [Circle Mirror][circle-mirror]
3. Sound-Effect

In this blog post, I will explain my idea and how I incorporate each one of them into one single piece of work. 

# Mouse Interaction

There are two mouse interaction, the mouse trail and mouse ripple.

Mouse trail is an array of circles that follow the mouse. The circles is white and positioned at the bottom after the background. The idea is this mouse trail acts like a flashlight so you can see what is happening on the screen. The mouse trail start of with a certain size, and gradually scale down and dissapear and new circle appears.

Mouse ripple is a group of three circles. When you click on the canvas, it will create three circle that start with size 0, and gradually scale up until it covers the whole canvas.

# Recursive Rectangle
In assignment 2, I use the recursive function on a rectangle. It might look simple at first, however after adding some random weight stroke and rotation on the rectangle, it created this spiral illusion.

The rectangles are black, the same colour as the background. You can only see it through the mouse trail, the mouse ripple and circle mirror.

# Circle Mirror
In the middle of the canvas, there is a dark grey circle. You can see the recursive rectangles on this circle more clearly if you hover over the mirror. The idea is to make the circle act as a window or mirror. You can peek on the recursive rectangle movement.


# Sound Effect
I have to say that sound is not the main character in this design. I added the sound effect just to enhance the interaction. As i mention at the end of [my previous blog post][previous-post], there were some problem with loading audio from p5.js to VSC. This is why i decided to change the audio button into a normal button/mirror with no audio function. 

To compensate the silentness in the design, I added a web audio API sampler that i learnt in creative coding class. This way, if you click on anypart of the screen, it will play a bell sound to accompany the ripple effect. 

Compared to the original code, I added a minus in front of the ypos so the y_ratio will have a negative value. This resulted in a deeper pitch sound instead of a higher one.

In addition to that, instead of using the mouse x position, i use the yposition. This way the audio pitch will be different depending on the `y_pos`. 

The reason why I changed all of that is to match the ripple interaction. If the mouse is on the top of the screen (low y value) it will play a high sound effect, and if the mouse is on the bottom of the screen (high y value) it will play a low sound effect.

{% highlight ruby %}
        function click_handler (mouse_event) { 
            if (audio_context.state == 'suspended') {
                audio_context.resume ()
            } else {
                // identify the mouseY position
                const y_pos = mouse_event.clientY
                
                // this is to get a ratio using the mouseY position and the canvas width
                // I set the y_pos into a negative value so that the audio will pitch lower
                const y_ratio = - y_pos / window.innerHeight

                // the ratio above is times with two to make it stronger, then the value will become the playback rate
                play_ding (2 ** y_ratio)
            }
        }
{% endhighlight %}
<br>

## Credit
My idea on how to incorporate the interaction, recursion and sound is inspired by a work called "[Love Will Tear Us Apart][qianqianye]" by Qianqian Ye. The rotating line in this work reminds me of a spider web. It is somewhat chaotic but also harmonized with the audio beat. Although the end result of my work doesn't really reflect my inspiration, it is still reflected in my progress, especially during the research for recursion.

Compilation of links: [Creative Coding Assignment 2 Research][creativecoding-assignment2-research]

[assignment2-fullscreen]: http://digitalmedia.rmit.edu.au/~s3862934/creativecoding_assignment2/

[mouse-interaction]: https://reilivia.github.io/creative/coding/2022/09/19/exploring-the-mouse-interaction-array.html
[recursive-rectangle]: https://reilivia.github.io/creative/coding/2022/09/20/exploring-the-recursion-function.html
[circle-mirror]: https://reilivia.github.io/creative/coding/2022/09/22/research-on-the-audio-interaction.html
[qianqianye]: https://qianqian-ye.com/Everyday/Day28/ 


[previous-post]: https://reilivia.github.io/creative/coding/2022/09/22/creating-the-circle-mirror.html

[creativecoding-assignment2-research]: http://digitalmedia.rmit.edu.au/~s3862934/creativecoding_assignment2_research/ 