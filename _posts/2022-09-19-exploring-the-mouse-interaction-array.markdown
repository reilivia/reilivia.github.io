---
layout: post
title:  "Exploring The Mouse Interaction Array"
date:   2022-08-21
categories: creative coding
---

# Research and Reference
To start of, I look for some reference to guide me how to create a mouse interaction with array. Then, I remember the website that I used for my last assignment to create bubble array. In this blog, I will explain my research in exploring the mouse trail function from [Happy Coding Array Tutorials][happycoding-array]. 

## Plan for Assignment 2

# Mouse Trail
In my attempt to check off the requirement to use array in assignment 2, I plan to create a mouse trail.

Following the [Happy Coding Array Tutorials][happycoding-array], I start of with creating an array to contain the circles. 

{% highlight ruby %}
let trail = [];
{% endhighlight %}

After that, create a mousetrail function. In this example, I get rid of the fill because i want to see the overlapping circles. 

{% highlight ruby %}
function mousetrail() 
{% endhighlight %}

Then, I add another function to pinpoint the location of the mouse do that the circle can trail behind the mouse

{% highlight ruby %}
  trail.push(new p5.Vector(mouseX, mouseY));
{% endhighlight %}

Considering that too many circles will overload the canvas, I add a conditional function so that if the trail length is more than a certain value, it will delete the end of the circle.

{% highlight ruby %}
  if (trail.length > 50) {
    trail.shift();
  }
{% endhighlight %}

Now that I have all that, I add the loop function for the trail itself. This way, the circle will over and over creating a trail.

{% highlight ruby %}
  for (let i = 0; i < trail.length; i++) {
    let p = trail[i];
  }
{% endhighlight %}

After setting up the location, I need to set up the size. I use the size variable to set the size to start with size 50 and scale down as the trail get longer. 

{% highlight ruby %}
  let size = (50.0 * i) / trail.length;
{% endhighlight %}

Finally, at the end of the 'mousetrail()' function is to create the circle itself.
{% highlight ruby %}
 circle(p.x, p.y, size);
{% endhighlight %}

# Mouse Ripple


[happycoding-array]: https://happycoding.io/tutorials/p5js/array-functions 