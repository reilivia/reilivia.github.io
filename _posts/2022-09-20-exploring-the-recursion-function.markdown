---
layout: post
title:  "Exploring The Recursion Function"
date:   2022-09-20
categories: creative coding
---

# What is Recursion?
Going into this research, I was still a bit confuse what recursion is. I understand that recursion is a function in itself, however it's a bit hard to come up with a simple idea using this function. This time, I'm going in blindly and just do some random research about recursive rectangels.

# Following Tutorials and Examples
Here are some tutorials and examples that I follow: 
1. [Recursion Blog from Creative Coding Class][creativecoding-recursion]
The best way to start this research is through the class material. Unfortunately, there are lots of thing going on in that blog post to the point that I was confused what's the meaning of recursion. After a while, i decided to try and see the simplest code among all of the examples.

2. [Recursive Rectangle from Creative Coding Class][creativecoding-recursiverectangle]
Personally, I think this is the simplest code among all the examples. I have to say that the end result is a bit hypnotic. I think the main issue for me when learning this function is how confusing the end result is (a thing inside a thing inside a thing... and so on). 

<div align ="center">
  <iframe width="576" height="366" src="https://editor.p5js.org/capogreco/full/iVA1FtAex"></iframe>
</div>
<br>

I stopped the preview and got rid of the random colour to look at the code carefully, I notice some point in this code. To have a recursion, you need to draw the function inside itself. 

{% highlight ruby %}
function recursive_rectangles (w, h) {
  if (w > 0 && h > 0) {
    rect (width / 2, height / 2, w, h)
    recursive_rectangles (w - 10, h - 10)
  }
{% endhighlight %}

3. [Coding Challenge #77: Recursion by The Coding Train][codingtrain-recursion]
Now that I somewhat understand what recursion function is, I tried to look for another example from an outside source. So, I watched a video called [Coding Challenge #77: Recursion by The Coding Train][codingtrain-recursion]. This video teached me about recursion in a more detailed manner. I figured out how to make the recursion more interactive by using `mouseX, mouseY` and even got some idea for my assignment 2.

# Recursion in Canvas API

<div align ="center">
  <iframe width="576" height="366" src="http://digitalmedia.rmit.edu.au/~s3862934/creativecoding_assignment2_research/recursiontest.html"></iframe>
</div>
<br>


[Click Here][js-recursiverectangle-canvasapi] if the embedded javascript doesn't work.

By this point I was confident enough about recursion and ready to dip my feet into using Canvas API. I tried to conver the recursive rectangle into Canvas API. Here are some things that I've done:

{% highlight ruby %}
<canvas id='recursive-rectangle'></canvas>
<script type='module'>
document.body.style.margin   = 0
document.body.style.overflow = `hidden`
document.body.bgColor        = `pink`

// get and format the canvas element
const cnv = document.getElementById ('recursive-rectangle')
cnv.width  = window.innerWidth
cnv.height = window.innerHeight
document.body.appendChild (cnv)

const ctx = cnv.getContext ('2d')


//--------------------------

// defining a function that takes two arguments
// which will be assigned to the parameters w & h
// ie. width and height
function recursive_rectangles (w, h) {
  
  // if width AND hight are both more than 0
  if (w > 0 && h > 0) {
    
    // get a rando colour for fill
    // var randomcolour = 'pink'
    // ctx.fillStyle = `randomcolour`

    const mid_x = window.innerWidth  / 2
    const mid_y = window.innerHeight / 2

    const x_pos = mid_x - (w / 2)
    const y_pos = mid_y - (h / 2)
    
    // draw a rectangle in the middle
    // of the canvas with the current
    // width and height parameters
    // ctx.fillRect (cnv.width / 2, cnv.height / 2, w, h)
    ctx.strokeRect (x_pos, y_pos, w, h)
    
    // call itself again, with smaller 
    // arguments for width & height 
    recursive_rectangles (w - 10, w - 10)
  }
}


recursive_rectangles (cnv.width, cnv.height)

</script>
{% endhighlight %}

After finishing this research, I tried to understand the other recursive examples, such as Recursive Tree Example with Canvas API. By this point, my head was overloaded with too much information to the point that I forget the main idea of what recursion is.

# My Plan for Assignment 2
1. [Recursion Illusion - P5.js by Oliver Dimes][recursionillusion-oliverdimes]
After all that hustle-bustle, I decided to take a step back and look for ideas in YouTube. This is where I found this example of [Recursion Illussion by Oliver Dimes][recursionillusion-oliverdimes]. I watched the video and thought that i might be able to do that for assignent 2. Little did i know, the recursion Canvas API research messed with my head to the point that I didn't realize this is not a recursive function.

<div align ="center">
  <iframe width="576" height="366" src="https://editor.p5js.org/reilivia/full/XQgFnLQiN"></iframe>
</div>
<br>

In conclusion, even though this is just a loop function, I can use this as an idea for my assignment 2. So, I decidd to make the recursive rectangle to rotate and create some kind of an illusion.

2. [Recursive Rectangle Web][recursiverectangle-web]

Moving on, I went back to the recursive rectangle and try to figure out how to iterate this simple code. I tried to put a random value for the difference between each recursion. This resulted in a cool graphic effect. 

<div align ="center">
  <iframe width="576" height="366" src="http://digitalmedia.rmit.edu.au/~s3862934/creativecoding_assignment2_research/recursiverectangle-random.html"></iframe>
</div>
<br>

[Click Here][js-recursiverectangle-random] if the embedded javascript doesn't work.

Seeing that the random variable is working, I went on to add random colour, random stroke weight and random rotation value. The result is quite surprising because it looks like a string web.

<div align ="center">
  <iframe width="576" height="366" src="http://digitalmedia.rmit.edu.au/~s3862934/creativecoding_assignment2_research/recursiverectangle-web.html"></iframe>
</div>
<br>

[Click Here][js-recursiverectangle-web] if the embedded javascript doesn't work.


I tried to look at the previous example of recirsive rectangle to see why the rectangle wont wove. Turns out, the rectangles was drawn outside the canvas because there is no limitation. So, i added an `if` function to contain the recursive rectangle. This way the rectangle is only drawn inside the canvas.

{% highlight ruby %}
function rectPattern(x, y, w, h) {
  noFill();

  if (w > 0 && h > 0) {
    rect(width / 2, height / 2, w, h);
     
    stroke(random(colours));
    strokeWeight(random(web));  

    rotate(frameCount * 0.05);
    rectPattern(x, y, w - 10, h - 10);
  }
}
{% endhighlight %}

<div align ="center">
  <iframe width="700" height="500" src="http://digitalmedia.rmit.edu.au/~s3862934/creativecoding_assignment2_research/recursiverectangle-rotate.html"></iframe>
</div>
<br>

[Click Here][js-recursiverectangle-rotate] if the embedded javascript doesn't work.


Check out how I incorporate this into my [Assignment 2][assignment2].


[creativecoding-recursion]: http://thomas.capogre.co/rmit/ccs/2022/09/03/recursion.html 
[creativecoding-recursiverectangle]: https://editor.p5js.org/reilivia/sketches/0-pUsdKF1
[codingtrain-recursion]: https://youtu.be/jPsZwrV9ld0 
[recurcivecircle]: https://editor.p5js.org/reilivia/sketches/vpL_2V4J1 
 
[recursionillusion-oliverdimes]: https://youtu.be/YxOc8AvwQtM
[recursiverectangle-web]: https://editor.p5js.org/reilivia/sketches/rGHajU-WE

[assignment2]: https://reilivia.github.io/creative/coding/2022/08/21/assignment-2-documentation.html 

[js-recursiverectangle-canvasapi]: http://digitalmedia.rmit.edu.au/~s3862934/creativecoding_assignment2_research/recursiontest.html 
[js-recursiverectangle-random]: http://digitalmedia.rmit.edu.au/~s3862934/creativecoding_assignment2_research/recursiverectangle-random.html

[js-recursiverectangle-web]: http://digitalmedia.rmit.edu.au/~s3862934/creativecoding_assignment2_research/recursiverectangle-web.html 
[js-recursiverectangle-rotate]: http://digitalmedia.rmit.edu.au/~s3862934/creativecoding_assignment2_research/recursiverectangle-rotate.html
