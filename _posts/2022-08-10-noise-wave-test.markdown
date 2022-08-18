---
layout: post
title:  "Wave Noise Test"
date:   2022-08-18
categories: creative coding
---

To start with, I was scolling down the examples in the p5js website and found the [Noise Wave][noise-wave] examples. I found this example interesting because it creates a wave like effect using noise. When i heard the word noise i imagine the black and white noise on the TV, this is whhy i wa interesting how can a noise create a wave like effect.
To understand the code, i copied it and set up several questions for myself.

[noise-wave]: https://p5js.org/examples/math-noise-wave.html 

<iframe src="https://editor.p5js.org/reilivia/full/Ullt443Y1"></iframe>

# Why use Begin Shape?
The code uses beginShape() to create a shape using vertex. Two of the vertex will be a noise line, while the other two are used to fill half of the canvas.

# What is Map and why use it in this code?
Coming into this research, I have no knowledge about map. Therefore I did some research about what map is by watching a YouTube video called [The map() Function - p5.js Tutorial][map-1] by The Coding Train and the [p5js map reference][map-2].

[map-1]: https://youtu.be/nicMAoW6u1g 
[map-2]: https://p5js.org/reference/#/p5/map 

{% highlight ruby %}
    let y = map(noise(xoff, yoff), 0, 1, height/2, height/2 + 50);
{% endhighlight %}

From there, I learnt that the map function in the code is meant to map the noise with 0-1 value on the canvas. I tried to change the value of the canvas several times and ended up with setting it into half of the canvas.

# What is offset value?
When encountered with an unfamliar code such as noise, the first thing i notice is the y offset on top of the sketch. To know what is an offset value, I tried to see [p5js noise reference][noise-1]. Unfortunately, there isn't any detailed explanation about offset in that page. So, I tried watching a YouTube video called [2D Noise - Perlin Noise and p5.js Tutorial][noise-2] by The Coding Train.

[noise-1]: https://p5js.org/reference/#/p5/noise 
[noise-2]: https://youtu.be/ikwNrFvnL3g 

From that video, I learnt that an offset is a value that the noise function takes to create a particular value relating to a particular axis. So if i use xoff and yoff, it will give me a particular noise value at a particular x location and y location in the canvas.

# What is Increment?



# Why does the y offset is outside the function, while the x offset is inside?

