---
layout: post
title:  "Understanding Hydra Function"
date:   2022-10-22
categories: creative coding
---

## Plan for Assignment 3

To learn hydra function, I did some experiments and played with the functions. I use two websites for reference, from the [hydra website] and from [clipsoundandmusic].

Hydra have five functions:
1. Source 
2. Geometry 
3. Color 
4. Blend 
5. Modulate 

Each hydra code always start with a source function, then transform with other functions, and finally end with an out() function.

Source function:
* noise (scale, offset)
    * Scale = control how many noise on screen
    * Offset = control the movement speed
* voronoi (scale, speed, blending)
    * Scale = control how many voronoi point on screen
    * Speed = control the movement speed
    * Blending = control the colour blend on each point
* osc (frequency, sync, offset)
    * Frequency = control how many black and white stripe on the screen
    * Sync = control the movement speed
    * Offset = control the colour offset
* shape( sides, radius, smoothing)
    * Sides = control how many side of the shape
    * Radius = control how big the shape is
    * Smoothing = control the blending of the shape
* gradient (speed)
    * Speed = control the movement speed

After understanding some of the source function that I plan to use, I explore some of the other function using those source function.

In this first example, I add `color()`, `kaleid()` , and `modulateRepeat()` functions. The `color()` function add a tint to the white part of the noise. The `kaleid()`  function give this kaleidoscope like effect to the noise. And the `modulateRepeat()` function will repeat the noise function and give this filter like function using source function as a texture.

<div align ="center">
  <iframe width="750" height="500" src="https://hydra.ojack.xyz/?code=bm9pc2UoNSUyQyUyMDAuMSklMEElMjAlMjAuY29sb3IoNSUyQzIlMkMzKSUwQSUyMCUyMC5rYWxlaWQoMTApJTBBJTIwJTIwLm1vZHVsYXRlUmVwZWF0KG9zYygxJTJDMSUyQzEpJTJDJTIwMy4wJTJDJTIwMy4wJTJDJTIwMC41JTJDJTIwMC41KSUwQSUyMCUyMC5vdXQobzAp"></iframe>
</div>
<br>

In the second example, I add `color()`, `rotate()` , and `ease()` functions. On the `rotate()` function, I add an array `[-0.5, 0.5]`. This is why the voronoi is rotating back and forth. Meanwhile, the `ease()` function is making the rotation to ease in and out.

<div align ="center">
  <iframe width="750" height="500" src="https://hydra.ojack.xyz/?code=dm9yb25vaSg1JTJDMC4zJTJDMC4zKSUwQSUyMCUyMC5jb2xvcig1JTJDMiUyQzEpJTBBJTIwJTIwLnJvdGF0ZSglNUItMC41JTJDMC41JTVEJTBBJTIwJTIwLmVhc2UoJ2Vhc2VJbk91dEN1YmljJykpJTBBJTIwJTIwLm91dChvMCk%3D"></iframe>
</div>
<br>

In the third example, I add `color()`, `pixelate()` , and `modulateScrollX()` functions. The `pixelate()` function create a pixel from the source function color. And the `modulateScrollX()` function move the original source function on X axis using an oscillator texture.s

{% highlight ruby %}
  .repeat(5, 5, () => Math.sin(time), () => Math.sin(time/2))
{% endhighlight %}

<div align ="center">
  <iframe width="750" height="500" src="https://hydra.ojack.xyz/?code=c2hhcGUoMiUyQzAuMSUyQzAuMSklMEElMjAlMjAuY29sb3IoMC4xJTJDMC45JTJDKCklMjAlM0QlM0UlMjAoYS5mZnQlNUIwJTVEKjQpKSUwQSUyMCUyMC5yZXBlYXQoNSUyQyUyMDUlMkMlMjAoKSUyMCUzRCUzRSUyME1hdGguc2luKHRpbWUpJTJDJTIwKCklMjAlM0QlM0UlMjBNYXRoLnNpbih0aW1lJTJGMikpJTBBJTIwJTIwLm91dChvMCk%3D"></iframe>
</div>
<br>


## Modulate Rotate experiment

In Creative Coding class, I did some experiments with a friend for `modulateRotate()` function. I thought that it is really interesting because it’s like a filter using texture in hydra. Using that code from class, I edited it and separate it into four frames to make it easier to play with the camera.

<div align ="center">
  <iframe width="750" height="500" src="https://hydra.ojack.xyz/?code=czAuaW5pdENhbSgpJTBBc3JjKHMwKSUwQS5jb2xvcigxJTJDMiUyQzkpJTBBJTIwJTIwLm1vZHVsYXRlUm90YXRlKHNoYXBlKDEwJTJDJTIwMC4yJTJDJTIwMC43KSUyQyUyMDMwKSUwQSUyMCUyMC5vdXQobzApJTNCJTBBJTBBc3JjKHMwKSUwQS5jb2xvcigxJTJDMiUyQzkpJTBBJTIwJTIwLm1vZHVsYXRlUm90YXRlKG5vaXNlKDEwJTJDJTIwMC4xKSUyQzAuNSklMEElMjAlMjAub3V0KG8xKSUzQiUwQSUwQXNyYyhzMCklMEEuY29sb3IoMSUyQzIlMkM5KSUwQSUyMCUyMC5tb2R1bGF0ZVJvdGF0ZSh2b3Jvbm9pKDUlMkMlMjAwLjElMkMlMjAwLjMpJTJDMTApJTBBJTIwJTIwLm91dChvMiklM0IlMEElMEFzcmMoczApJTBBLmNvbG9yKDElMkMyJTJDOSklMEElMDkubW9kdWxhdGVSb3RhdGUob3NjKDEwKSUyQzMwKSUwQSUyMCUyMC5vdXQobzMpJTNCJTBBJTBBcmVuZGVyKCklM0IlMEElMEE%3D"></iframe>
</div>
[Click here to open the website]
<br>


[hydra website]: https://hydra.ojack.xyz/docs/#/getting_started  
[clipsoundandmusic]: https://www.clipsoundandmusic.uk/hydra-tutorial-a-beginners-guide-to-live-coding-visuals/ 
[Click here to open the website]: https://hydra.ojack.xyz/?code=czAuaW5pdENhbSgpJTBBc3JjKHMwKSUwQS5jb2xvcigxJTJDMiUyQzkpJTBBJTIwJTIwLm1vZHVsYXRlUm90YXRlKHNoYXBlKDEwJTJDJTIwMC4yJTJDJTIwMC43KSUyQyUyMDMwKSUwQSUyMCUyMC5vdXQobzApJTNCJTBBJTBBc3JjKHMwKSUwQS5jb2xvcigxJTJDMiUyQzkpJTBBJTIwJTIwLm1vZHVsYXRlUm90YXRlKG5vaXNlKDEwJTJDJTIwMC4xKSUyQzAuNSklMEElMjAlMjAub3V0KG8xKSUzQiUwQSUwQXNyYyhzMCklMEEuY29sb3IoMSUyQzIlMkM5KSUwQSUyMCUyMC5tb2R1bGF0ZVJvdGF0ZSh2b3Jvbm9pKDUlMkMlMjAwLjElMkMlMjAwLjMpJTJDMTApJTBBJTIwJTIwLm91dChvMiklM0IlMEElMEFzcmMoczApJTBBLmNvbG9yKDElMkMyJTJDOSklMEElMDkubW9kdWxhdGVSb3RhdGUob3NjKDEwKSUyQzMwKSUwQSUyMCUyMC5vdXQobzMpJTNCJTBBJTBBcmVuZGVyKCklM0IlMEElMEE%3D