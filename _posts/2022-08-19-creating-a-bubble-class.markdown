---
layout: post
title:  "Creating a Bubble Class"
date:   2022-08-19 11:54:00 +1000
categories: creative coding
---

In this blog post I will explain my thought proccess in understanding class and array by going through a p5js tutorial by [happycoding][happycoding]. Then I will explain my plan in applying my research into my assignment 1.

# First Encounter with .js Class
Coming into this, I have experience working with classes in HTML and CSS. Therefore, I was a bit confuse with class in javascript. The main reason is with how you need to set up a variable first, then add the class functions.

# Plan for Assignment 1
Why do I follow through this tutorial? Because I want to learn the base knowledge of creating a class in p5js.

One of my plans for assignment 1 is to create a class for bubbles. The bubbles will float around the canvas with different size and speed.

# Following [happycoding][happycoding] Tutorials 

In the tutorial, I started with creating a bouncing circle with the draw function and then convvert it into a class function. Then, change the main variable into array and add a loop function to make x number of bouncing circles.

<div align ="center">
  <iframe width="400" height="442" src="https://editor.p5js.org/reilivia/full/PmzQ3PG4u"></iframe>
</div>
<br>

Overall, the tutorials by [happycoding][happycoding] is not that different from the one I get in creative coding class. However, I was able to understand it better by walking through it on my own pace.

<br>
<br>

## Creating My Bubble Class

In attempting to create my own bubble class, I started with creating the class for bubble. To make the bubble float upward with random size, I will need a `ySpeed` and `size` in addition to `x` and `y` position.

{% highlight ruby %}
class bubble {
  constructor(x, y, ySpeed, size) {
    this.x = x;
    this.y = y;
    this.ySpeed = ySpeed;
    this.size = size;
  }
{% endhighlight %}

Then, I set up an array for Bubbles and put it on top of the sketch.

{% highlight ruby %}
let Bubbles = []
{% endhighlight %}


After that, I created a new instance for the bubbles in the setup function. There will be about 50 bubbles floating on the canvas. I set the bubble to have random position on the `x axis`, random `xSpeed` and random `size` within a certain value. All the bubbles will start at the bottom of the canvas.

{% highlight ruby %}
  for(let i = 0; i < 50; i++) {
    Bubbles[i] = new bubble(random(width), height, random(-2, 2), random(15))
  }
{% endhighlight %}

Next, I created a `float` function and add the function to the draw function. The float function will let the bubble to move on the y axis at a certain speed. If the bubble is less than 0 or more than the height, the function will bring it back at the bottom of the canvas so it will loop back and float upwards.

{% highlight ruby %}
  float() {
    this.y += this.ySpeed;
    if (this.y < 0 || this.y > height) {
      this.y += height;
    }
  }
{% endhighlight %}

Last but not least, I created a class function called `show` and add the function to the draw function. This will create a circle for the bubble.

{% highlight ruby %}
  show() {
    circle(this.x, this.y, this.size);
  }
{% endhighlight %}

<br>
<br>

Check out how I embed the bubbles into my [Assignment 1][assignment1].


[happycoding]:https://happycoding.io/tutorials/p5js/creating-classes 

[assignment1]:https://reilivia.github.io/creative/coding/2022/08/20/assignment-1-documentation.html 