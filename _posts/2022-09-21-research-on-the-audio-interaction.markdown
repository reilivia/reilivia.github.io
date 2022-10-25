---
layout: post
title:  "Research on the Audio Interaction"
date:   2022-09-21
categories: creative coding
---

# Plan for Assignment 2
For asignment 2, I wanted to add a simple sound on-click event to enhace the interaction in my design. The examples on the Creative Coding materials are all interesting, however, they are too complicated for me because most of the are in Canvas API. Thus, I went with my second best choice of reference, the p5.js library. In that library, I found a [Sound Effect Example][p5-soundeffect]. This example contains a button that plays a sound on-click. In addition to that, this can check off the requirement to use `class` in my code.

# Research

I followed the [Sound Effect Example][p5-soundeffect] and managed to understand how the code works. Here's my notes in following this example:
1. Set the audio file and button variable.
{% highlight ruby %}
let audioFile;
let button;
{% endhighlight %}

2. Load the audio file on the setup function.
{% highlight ruby %}
 soundFormats("mp3", "ogg");
  audioFile = loadSound("audio.mp3");
{% endhighlight %}

3. Create a class for the button.
{% highlight ruby %}
class myButton {
    constructor(x, y, r) {
        this.x = x;
        this.y = y;
        this.r = r;
    }
  }
{% endhighlight %}

4. Identify the mouse position on the button. 
{% highlight ruby %}
  contains(mx, my) {
    return dist(mx, my, this.x, this.y) < this.r;
  }
{% endhighlight %}

5. Add a display function to show the button. The `if()` function will create a hover effect for the button.
{% highlight ruby %}
display(mx, my) {
    // Colour on mouse over
    if (this.contains(mx, my)) {
      fill("black");
      stroke("white");
    }
    // Colour on mouse out
    else {
      fill("white");
      stroke("black");
    }
    strokeWeight(5);
    ellipseMode(RADIUS);
    ellipse(this.x, this.y, this.r, this.r);
  }
}
{% endhighlight %}

6. On the `mousePressed()` function, add an if function so that the audio will pa=lay whan the mouse pressed the button.
{% highlight ruby %}
if (button.contains(mouseX, mouseY)) {
    audioFile.play();
  }
{% endhighlight %}

After I figured out how the audio button work, I wanted to add another sound. My plan is, if you click on the button, it will play/stop the music. And if you just click any part of the canvas, a short sound effect will play. This way you can interact with the music too.

To do that, I checked out another p5 example called [Load and Play Sound][p5-loadnplaysound]. Essentially, this example let you play and stop the sound on click. I tried to combine both code by putting the `if()` function that play/stop audio inside the `if()` function that identify the button position. 

{% highlight ruby %}
function mousePressed() {
  // If you click the button it will do play/stop the audio
  if (button.contains(mouseX, mouseY)) {
    if (audioFile.isPlaying()) {
      audioFile.stop();
    } else {
      audioFile.play();
    }
  }

  // play audio if you click on any part of the canvas
  audioBG.play();
}
{% endhighlight %}

<div align ="center">
  <iframe width="576" height="366" src="https://editor.p5js.org/reilivia/full/gwyFINWyR"></iframe>
</div>
<br>


# Research

Although the idea for the button works really well in p5.js, it is not working when i move it into Visual Studio Code. Apperently there were some problem with uploading the audio file. Unfortunately, i can't spend my time dwelling in this, so i just abort the plan and move on to the next plan. 

My other plan is to use the audio example that play the audio onlick and change the audio pitch based on the mouseX mosition. This is the example from the creative coding class. 

<div align ="center">
  <iframe width="576" height="366" src="http://digitalmedia.rmit.edu.au/~s3862934/creativecoding_assignment2_research/bubblesound.html"></iframe>
</div>
<br>

[Click Here][js-bubblesound] if the embedded javascript doesn't work.

In here, I don't really change much of the code and the comment. I just change the audio because I was trying to understand how the audio work in canvas API. I will explain my intention more detailed in the assignment 2 documentation.

Check out how I incorporate this into my [Assignment 2][assignment2].



[p5-soundeffect]: https://p5js.org/examples/sound-sound-effect.html 
[p5-loadnplaysound]: https://p5js.org/examples/sound-load-and-play-sound.html 

[assignment2]: https://reilivia.github.io/creative/coding/2022/08/21/assignment-2-documentation.html 

[js-bubblesound]: http://digitalmedia.rmit.edu.au/~s3862934/creativecoding_assignment2_research/bubblesound.html 