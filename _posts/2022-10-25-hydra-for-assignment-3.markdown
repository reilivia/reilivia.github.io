---
layout: post
title:  "Hydra for Assignment 3"
date:   2022-10-25
categories: creative coding
---

For assignment 3, I’m using hydra because it is visually appealing. It is easy to access on any device.

## Initial Idea

Initially, my plan is to create a visual code that uses camera function. I got this idea when I saw [Olivia Jack’s Portfolio], specifically, the [Selfie Apocalypse] project. 

When i saw that work, i got this flashback of memories about my friends. We used to play with social media camera function when filter started to become a trend. For me at that time, it’s not about taking picture. It's about playing around and trying different filters. 

My goal in designing this project is to connect with my old friends by socializing without words.

After I watched [Olivia Jack’s video about Hydra], I realized that Hydra aligns with my goal. In her presentation video, Olivia Jack mention how Hydra can be a way to socialize and interact with each other. 

## Hydra for Assignment 3

<div align ="center">
  <iframe width="750" height="500" src="https://hydra.ojack.xyz/?sketch_id=cS9xYao4gt7aaSxb "></iframe>
</div>
[Click here to open the website]
<br>


In this project, I use multiple output to have four frames of output. Before start coding all four output, I put a function to initialized the camera for this website. Therefore, all the source function for four outputs are the camera. Although all of them uses the same source function, they have different transformation.

1. Output 1 `out(o1)`
* `.color(1, 1.5, 5)` - give a blue-ish colour
* .modulateRepeat(osc(10), 3.0, 3.0, 0.5, 0.5) - modulate the source function using oscillator as a texture and repeat it into a 3 by 3 frame.  This create a wave like movement.
* `.blend(noise(0.5, 0.5), 0.3)` - blend the screen with noise. This create a noise-like texture on top of this output. Since I only put a small number for each value, this will only give a light and dim effect.

2. Output 2 `out(o2)`
* `.color(1, 1, 2)` - give a purple-ish colour
* `.modulate(voronoi(1, 0.1, 0.1), 10)` - this will modulate the source code using voronoi texture. I give the voronoi a small value so you can still distinguish the camera recording. The offset (last value) will set how much the voronoi will transform the source code.

3. Output 3 `out(o3)`
* `.color(2, 1, 1)` - give a red-ish colour
* `.modulate(osc(0.1,0.1,2), -1)` - this will give a filter like effect by modulating the source function with an oscillator texture.
* `.kaleid(3)` - this create a kaleidoscope effect
* `.rotate( () => time%360 )`- this will let all the previous function to rotate. Every time it rotates 360 degree, it will repeat the rotating.

4. Output 4 `out(o4)`
* `.color(1, 1.5, 5)` - give a blue-ish colour
* `.repeat(3, 3)`
* `.pixelate(100,100)`
* `.modulate(shape(100, () => (a.fft[0])/2, () => (a.fft[0])), () => (a.fft[0]*4))` - this will modulate the source function  using a shape as texture. This is why there is a sale iin the middle of the screen. I set the side to 100 to make the shape full circle. Meanwhile, I set all the other value into `() => (a.fft[0])` which let the value change based on the audio input. This way, the circle will get bigger and smaller based on how loud the user is.

Personally, I know that the code are nothing fancy. I figure that a complicated code will create a complicated visual. A complicated visual will transform the source function into something amazing, but indistinguishable. I want to still see the source function (the camera) because I want to see my family’s and friend’s faces. 
Another thing that need to be mentioned is the fact that I added an audio input (which is not in my initial idea) because I want to add more interaction to the design.


## Assignment 3 Community Practice

After finishing the code, I contacted some of my friends. I used social media such as LINE and WhatsApp to contact them. I asked them to interact with the website and record themself. I also video-called some of them to get the first genuine reaction. It was a bit hard considering that some of them don’t know how to record their screen or what to do with it. I had to give some direction and suggestions on what they can do.

What can you do? :)
1. Make a sound (clap, speak, or scream)
2. Make a movement (head, hand, device)
3. Just play with it!

When they opened the website, some of them had difficulties because hydra asked to use camera and microphone. After giving permission, their fist reaction was confused because of the code on the screen. It should be noted that 80% of them are not familiar with coding. Because of the suggestion that I gave, they start to move around, making sounds and just playing around. 

I asked them what they thought of it afterwards, they said:
* “I thought it still under development because there’s code on top of it”
* “It’s quite random, but wow”
* “It’s confusing, but it’s okay”
* “It’s amazing that you can make that with just some words”
* “That’s really fun”
* “It’s a bit confusing on how to use it. It’s more like a Photo Booth but without the recording function. Overall, it’s cute and fun. There’s interaction with movement and sound”


While those who are familiar with code said: “It is fun. Less code can do lots of things”


## Conclusion
Community of Practice (CoP) = friends
* domain = social media (LINE, WhatsApp, Discord, WeChat)
* repertoire = sitting down, moving around, clapping, speaking.
* values = fun, confused, amazed.








[Olivia Jack’s Portfolio]: https://ojack.xyz

[Selfie Apocalypse]:https://ojack.xyz/articles/selfie-apocalypse/index.html

[Olivia Jack’s video about Hydra]: https://www.youtube.com/watch?v=cw7tPDrFIQg

[Click here to open the website]: https://hydra.ojack.xyz/?sketch_id=cS9xYao4gt7aaSxb 