---
layout: post
title:  "Exploring The Mouse Interaction Array"
date:   2022-09-19
categories: creative coding
---

# Research and Reference
To start of, I looked for some reference to guide me on how to create a mouse interaction with array. Then, I remembered the website that I used for my last assignment to create the bubble array. 

In this blog, I will explain my research in exploring the mouse trail function from [Happy Coding Array Tutorials][happycoding-array] and my research on the [Mouse Ripple Example][happycoding-mouseripple].

# Mouse Trail
In my attempt to check off the requirement to use array in assignment 2, I planned to create a mouse trail.

Following the [Happy Coding Array Tutorials][happycoding-array], I started of with creating an array to contain the circles. 

{% highlight ruby %}
let trail = [];
{% endhighlight %}

After that, I created a mousetrail function. In this example, I got rid of the fill because I wanted to see the overlapping circles. 

{% highlight ruby %}
function mousetrail() 
{% endhighlight %}

Then, I added another function to pinpoint the location of the mouse do that the circle can trail behind the mouse

{% highlight ruby %}
  trail.push(new p5.Vector(mouseX, mouseY));
{% endhighlight %}

Considering that too many circles will overload the canvas, I added a conditional function so that if the trail length is more than a certain value, it will delete the end of the circle.

{% highlight ruby %}
  if (trail.length > 50) {
    trail.shift();
  }
{% endhighlight %}

Now that I have all that, I added the loop function for the trail itself. This way, the circle will over and over creating a trail.

{% highlight ruby %}
  for (let i = 0; i < trail.length; i++) {
    let p = trail[i];
  }
{% endhighlight %}

After setting up the location, I set up the size. I set the size to start with size 50 and scale down as the trail get longer. 

{% highlight ruby %}
  let size = (50.0 * i) / trail.length;
{% endhighlight %}

Finally, I added a circle at the end of the `mousetrail()` function is to create the circle itself.
{% highlight ruby %}
 circle(p.x, p.y, size);
{% endhighlight %}

# Mouse Ripple
Another thing that I wanted to add to my design is a mouse ripple interaction. I found this [Mouse Ripple][happycoding-mouseripple] example from the Happy Coding website. To understand that code, I watched the video tutorials by The Coding Train called "[2.1: Variables in p5.js (mouseX, mouseY) - p5.js Tutorial][thecodingtrain-variable]". This video explain how to use the variable `(mouseX, mouseY)`. Through this video I was able tounderstand how to draw an object on mouse click.

The code in the [Mouse Ripple][happycoding-mouseripple] example starts of with setting variables for the circle position and size.

{% highlight ruby %}
let circleX;
let circleY;
let circleSize;
{% endhighlight %}

After that, I set the value for the circle's position and size in the setup function.

{% highlight ruby %}
circleX = width / 2;
circleY = height / 2;
circleSize = 0;
{% endhighlight %}

To make a ripple effect, the circle has to scale up over time. This function below is the one that increase the circle size value overtime.
{% highlight ruby %}
circleSize += 10;
{% endhighlight %}

Then, I added the circle function to draw the circle for the ripple. In this example, there are three circle with different size to create that ripple effect.

{% highlight ruby %}
circle(circleX, circleY, circleSize);
circle(circleX, circleY, circleSize * .75);
circle(circleX, circleY, circleSize * .5);
{% endhighlight %}

Finally, define the circle position to `mouseX` and `mouseY` so that it will create circles on mouse-click.

{% highlight ruby %}
function mousePressed(){
  circleX = mouseX;
  circleY = mouseY;
  circleSize = 0;
}
{% endhighlight %}

## Plan for Assignment 2
For assignment 2, I plan to incorporate both mouse trail and mouse ripple for the interaction.

<div align ="center">
  <iframe width="576" height="366" src="https://editor.p5js.org/reilivia/full/cQq77Sgr-"></iframe>
</div>
<br>

Check out how I incorporate this into my [Assignment 2][assignment2].

[happycoding-array]: https://happycoding.io/tutorials/p5js/array-functions 
[happycoding-mouseripple]: https://happycoding.io/examples/p5js/input/mouse-ripple 
[thecodingtrain-variable]: https://youtu.be/7A5tKW9HGoM

[assignment2]: https://reilivia.github.io/creative/coding/2022/08/21/assignment-2-documentation.html 
