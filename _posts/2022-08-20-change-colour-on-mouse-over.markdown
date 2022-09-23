---
layout: post
title:  "Change Colour on Mouse Over"
date:   2022-08-20 11:54:00 +1000
categories: creative coding
---

In this blog post, I will explain my journey in trying to create a change colour function on mouse over. 

# [Example by Akroll][hoverrectangle]

For assignment 1, I want to add a simple function where you can hover over the text and change the colour theme. To do that, I looked for a hover button examples on google and found this [example by akroll][hoverrectangle]. 

<div align ="center">
  <iframe width="400" height="442" src="https://editor.p5js.org/akroll/full/Hk7hFslhX"></iframe>
</div>
<br>

In the example above, the rectangle will change colour when you hover a certain area of the canvas.

## My Plan for Assignment 1

Inspired by the example above, I tried to create my own code by combining the if mouse over funtion with text using custom functions.

<div align ="center">
  <iframe width="576" height="366" src="https://editor.p5js.org/reilivia/full/HubEo-yfq"></iframe>
</div>
<br>

# Setting up the Text
* First I added the fonts in the preload function.
{% highlight ruby %}
function preload () {
  aclonica = loadFont ('fonts/Aclonica-Regular.ttf')
  princessSofia = loadFont ('fonts/PrincessSofia-Regular.ttf')
}
{% endhighlight %}

* Then, I created a custom function for the text and add the funtion in the draw function. I positioned the text in the middle of the canvas
{% highlight ruby %}
function textContent() {
  fill (225)
  textFont (aclonica)
  textSize (72)
  text (`RMIT`, width / 3, height / 2 - 30)

  fill (227, 229, 224)
  textFont (princessSofia)
  textSize (32)
  text (`Creative Coding`, width / 3, height / 2 + 15)
  text (`Specialisation`, width / 3 + 30, height / 2 + 50)
}
{% endhighlight %}


# The Change Colour Function
* The `changeColour()` function uses an `if` function and need 4 coordinates to define the mouse over area. Therfore, I used a `console.log` to help me know the area behind the text. In the example below, the function will create a gray rectangle on a black background. And if you hover over the rectangle, the background will change into hotpink and the rectangle will change into brown.
{% highlight ruby %}
function changeColour() {
  function changeColour() {
  if ((mouseX > 180) && (mouseX < 395) &&
  (mouseY > 70) && (mouseY < 140)) {
  background('hotpink')
  fill('brown')
  } 
  else {
  background('black')
  fill('gray')
  }
  rect(180, 70, 215, 70)
}
{% endhighlight %}

* Considering that I have another set of words below the `RMIT` word, I added another rectangle and an `else if` function.

{% highlight ruby %}
function changeColour() {
 if ((mouseX > 180) && (mouseX < 395) &&
  (mouseY > 70) && (mouseY < 140)) {
  background('hotpink')
  fill('brown')
  } 
  else if ((mouseX > 180) && (mouseX < 395) &&
  (mouseY > 150) && (mouseY < 225)) {
  background('blue')
  fill('black')
  } 
  else {
  background('black')
  fill('gray')
  }
  rect(180, 70, 215, 70, 20)
  rect(180, 150, 215, 75, 20)
  }
{% endhighlight %}

 
[hoverrectangle]: https://editor.p5js.org/akroll/sketches/Hk7hFslhX