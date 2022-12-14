---
layout: post
title:  "Exploring The Noise Wave"
date:   2022-08-18 21:44:00 +1000
categories: creative coding
---

To start with, I was scrolling down the examples in the p5js website and found the [Noise Wave][noise-wave] examples. I found this example interesting because it creates a wave like effect using noise. When I heard the word noise I imagine the black and white noise on the TV, this is why I was interesting to see how can a noise create a wave like effect. If possible, I want to use it as a background for my first sssignment.

To understand the code, I copied it and set up several questions for myself.

<div align ="center">
  <iframe width="400" height="442" src="https://editor.p5js.org/reilivia/full/Ullt443Y1"></iframe>
</div>
<br>

# Why use Begin Shape?
The code uses [beginShape()][begin-shape] to create a shape using vertex. Two of the vertex will be a noise line, while the other two are used to fill half of the canvas.

{% highlight ruby %}
//The wave is on the top part of the canvas
  vertex(width, 0);
  vertex(0, 0);
{% endhighlight %}

{% highlight ruby %}
//The wave is on the bottom part of the canvas
  vertex(width, height);
  vertex(0, height);
{% endhighlight %}

I tried to cahnge the value of the vertex to see how it affect shape of the noise wave. As you can see from the code above, I manage to make the wave upside down by changing the value of the two vertex.

# What is Map and why use it in this code?
Coming into this research, I have no knowledge about map. Therefore I did some research about what map is by watching a YouTube video called [The map() Function - p5.js Tutorial][map-1] by The Coding Train and the [p5js map reference][map-2].

{% highlight ruby %}
    let y = map(noise(xoff, yoff), 0, 1, height/2, height/2 + 50);
{% endhighlight %}

From there, I learnt that the map function in the code is meant to map the noise with 0-1 value on the canvas. I tried to change the value of the canvas several times and ended up with setting it into half of the canvas.

# What is offset value?
When encountered with an unfamliar code such as noise, the first thing i notice is the y offset on top of the sketch. To know what is an offset value, I tried to see [p5js noise reference][noise-1]. Unfortunately, there isn't any detailed explanation about offset in that page. So, I tried watching a YouTube video called [2D Noise - Perlin Noise and p5.js Tutorial][noise-2] by The Coding Train.

{% highlight ruby %}
let xoff = 0;
{% endhighlight %}

{% highlight ruby %}
let yoff = 0;
{% endhighlight %}

From that video, I learnt that an offset is a value that the noise function takes to create a particular value relating to a particular axis. So if i use xoff and yoff, it will give me a particular noise value at a particular x location and y location in the canvas. In addition to that, the offset value has to be 0-1 in order to make a 2D Perlin Noise.

# What is Increment?
In the original [Noise Wave][noise-wave] examples, there is this comments about increments.

{% highlight ruby %}
 // Increment x dimension for noise
    xoff += 0.05;
{% endhighlight %}

{% highlight ruby %}
 // Increment y dimension for noise
    yoff += 0.01;
{% endhighlight %}

According to the [2D Noise - Perlin Noise and p5.js Tutorial][noise-2] by Coding Train, increment is the value of how much the x or y offset will change.

# Why does the y offset is outside the function, while the x offset is inside?

When I watched the [2D Noise - Perlin Noise and p5.js Tutorial][noise-2] by Coding Train, I noticed that [in the beginning][noise-1d], there is only an x offset because it was a 1D Perlin Noise. [Later on in the video][noise-2d], a y offset was added to create a 2D Perlin Noise. 

Now, if you look closely in the original [Noise Wave][noise-wave] examples, the y offset is outside the shape , while the x offset inside. 

Here's what i got from my underestanding:
* The x offset is inside to reset the x offset of the shape back to zero (it will reset after the function). 
* The y offset is outside the loop so that the y offset increase by one on each line (keeping track so that it won't reset after the function).
* The x offset control the fluidity of the wave. 
* The y offset control the speed of the wave.

<br>
<br>

## Noise Wave in Assignment 1
After doing my research, I plan to add this noise wave into my assignment 1 as a background. 

Here is my version of the noise wave:

<div align ="center">
  <iframe width="576" height="366" src="https://editor.p5js.org/reilivia/full/WMf3A7mvE"></iframe>
</div>
<br>

* First of all, I change the variable name for fractical reason. From `xoff` into `fluidity`, and from `yoff` into `speed`.

* Since the Assignment 1 require me to use a certain size of canvas, I have to change the size of the canvas. However, there are some problem with the noise wave after i hange the canvas size. The width of the noise wave is not long enough to fill the width of the canvas. Therefore, i added `+ 10` to the x inside the loop.

{% highlight ruby %}
for (let x = 0; x <= width + 10; x += 10) {
    let y = map(noise(fluidity, speed), 0, 1, height/6, height/6 + 200)
    vertex(x, y)
    fluidity += 0.025
  }
{% endhighlight %}

* I set the fluidity valueand speed value to be low so that it will produce a smooth water-like effect.

{% highlight ruby %}
  // control the fluidity of the wave (jagged or smooth)
    fluidity += 0.025
{% endhighlight %}

{% highlight ruby %}
  // change the speed of the wave
    speed += 0.01
{% endhighlight %}

* Change the colour of the background and the wave into blue.
{% highlight ruby %}
  background('#00223d')
  fill ('#004281')
{% endhighlight %}


* Add another vertex between the vetexes on the corner. The added vertex will be at the middle-bottom of the canvas so that it will create a V line between the wave. The reason why I did this is because I plan to use the wave noise as a background and there will be texts in the middle of the canvas.

{% highlight ruby %}
  vertex(width, 0)
  vertex(width / 2, height)
  vertex(0, 0)
{% endhighlight %}

<br>
<br>

Check out how I embed my version of the noise wave into my [Assignment 1][assignment1].


[noise-wave]: https://p5js.org/examples/math-noise-wave.html 

[begin-shape]:https://p5js.org/reference/#/p5/beginShape

[map-1]: https://youtu.be/nicMAoW6u1g 
[map-2]: https://p5js.org/reference/#/p5/map 

[noise-1]: https://p5js.org/reference/#/p5/noise 
[noise-2]: https://youtu.be/ikwNrFvnL3g 

[noise-1d]:https://youtu.be/ikwNrFvnL3g?t=505  
[noise-2d]:https://youtu.be/ikwNrFvnL3g?t=532   

[assignment1]:https://reilivia.github.io/creative/coding/2022/08/20/assignment-1-documentation.html 