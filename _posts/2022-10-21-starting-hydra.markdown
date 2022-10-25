---
layout: post
title:  "Starting Hydra"
date:   2022-10-21
categories: creative coding
---

This blog is about my experience in exploring hydra for the first time.

## Starting Hydra

Hydra is not as well known as P5.js. Thus there are not many tutorials about it. The best way to learn it is through the website itself. I started my learning journey by following the tutorial on the [Hydra website]. 


The tutorial started with introducing the editor interface. 
I find the share function interesting because you can save your design and share it on the hydra Twitter account. It’s like communicating with code. 

After that, I copy paste the code into the tutorial.

{% highlight ruby %}
osc().out()
{% endhighlight %}


When I run the program, the screen shows straight black-and-white lines. This function is an oscillator. The function work this way:

{% highlight ruby %}
osc(frequency, sync, colour offset).out()
{% endhighlight %}

<div align ="center">
  <iframe width="750" height="500" src="https://hydra.ojack.xyz/?code=b3NjKDUlMkMlMjAtMC4xMjYlMkMlMjAwLjUxNCkub3V0KCk="></iframe>
</div>
<br>

All I need to do is change the value of the frequency, sync, and colour offset to get a gradient. If I add a rotate() function before the out() function, it will let the colour wave move to a certain degree.

After getting to this point, I read the whole “Getting Started” page on my own. It is quite redundant to paraphrase every single step I took in the tutorial for this blog because the tutorial itself is easy to understand. 

Here are some examples of my experiments when I play around with hydra:


<div align ="center">
  <iframe width="750" height="500" src="https://hydra.ojack.xyz/?code=b3NjKDEwKS5jb2xvcig1KS5rYWxlaWQoNSkub3V0KCklMEElMEElMEE%3D"></iframe>
</div>
<br>
<div align ="center">
  <iframe width="750" height="500" src="https://hydra.ojack.xyz/?code=c2hhcGUoNSkucmVwZWF0KCkucm90YXRlKDUpLnNjcm9sbFgoMCUyQyUyMDAuMSkub3V0KCklMEE%3D"></iframe>
</div>
<br>
<div align ="center">
  <iframe width="750" height="500" src="https://hydra.ojack.xyz/?code=czAuaW5pdENhbSgpJTNCJTBBc3JjKHMwKSUwQSUwOS5jb2xvcigxJTJDJTIwMiUyQyUyMDMpJTBBJTA5LnJvdGF0ZSgtNDUpJTBBJTA5Lm91dChvMCklMEFub2lzZSg5LjA5MiklMEElMDkuY29sb3IoMyUyQyUyMDIlMkMlMjAxKSUwQSUwOS5vdXQobzEpJTNCJTBBb3NjKCklMEElMDkuY29sb3IoMyUyQyUyMDIlMkMlMjAxKSUwQSUwOS5vdXQobzIpJTNCJTBBc3JjKG8wKSUwQSUwOS5jb2xvcigzJTJDJTIwMiUyQyUyMDUpJTBBJTA5LnJvdGF0ZSg5MCklMEElMjAlMjAuYmxlbmQobzEpJTBBJTIwJTIwLmJsZW5kKG8yKSUwQSUwOS5vdXQobzMpJTNCJTBBJTJGJTJGJTIwc2hvdyUyMGFsbCUyMG91dHB1dHMlMEFyZW5kZXIoKSUzQg%3D%3D"></iframe>
</div>
<br>

[Hydra website]: https://hydra.ojack.xyz/docs/#/getting_started  

