---
layout: post
title:  "I C What You Did There"
date:   2021-08-17 22:32:43 -0700
categories: C histoy background Unix Multics PDP-7 Bell Labs Dennis Ritchie Ken Thompson Brian Kernighan
---

# Introduction
I C you C we all C for icecream? Okay, I'll stop replacing C for see (even if it pains me). Instead, let's discuss 'C' - the language behind the languages! Where does it come from? Who are the men behind it? And, where is C most prevalent today?

# Background
So what exactly is C? C is a general purpose programming language used as the de-facto language in operating system development. It often acts as a middle man between higher level languages and low level assembly languages.

# Ken Thompson and Dennis Ritchie
Who are these sultans of software? Together they created programming paradigmns you could not live without. Originally working together on the [Multics][Multics] operating system at [Bell Labs][Bell Labs], Ken and Dennis cobbled together a new operating system on a [PDP-7][PDP-7] they had lying around. Coined ['Unix'][Unix] by [Brian Kernighan][Brian Kernighan], it would go on to be the founding force behind the C language and inspiration for the world famous Linux and iOS.

# C Development
Ken Thompson and Dennis Ritchie developed the Unix operating system in assembly language. Eventually wanting to not claw their eyes out (coding in assembly sucks), Ken sought out to create a new language to redesign Unix with. Cutting down the somewhat well known [BCPL][BCPL] language into something more workable, Thompson first designed and coined 'B'. Over time, Dennis worked to improve B and created what we now know as 'C'. By Unix V4, C was doing the heavy lifting.

# C Today
Even though C has morped into other well known languages like C++ and C#, it is still one of the world's most used software tools. Mostly used to interact with embedded systems, C is behind the oeprating systems of Windows, Linux, MacOS, iOS, Android, and even the now extinct Windows Phone. Famous database systems like Oracle, MySQL, and PostgreSQL have all been written in C. Many of our home electronics are written in C like your coffee maker, toaster, or even TV.

# Terms
[Operating Systems][Operating Systems]
[Multics][Multics]
[Unix][Unix]
[PDP-7][PDP-7]
[BCPL][BCPL]

# Appendix
http://jekyllbootstrap.com/lessons/jekyll-introduction.html#:~:text=The%20following%20is%20an%20outline%20of%20how%20that%27s,and%20templates.%20...%204%20Jekyll%20generates%20output.%20

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[BCPL]: https://www.bell-labs.com/usr/dmr/www/bcpl.html
[Bell Labs]: https://en.wikipedia.org/wiki/Bell_Labs
[Brian Kernighan]: https://www.cs.princeton.edu/~bwk/ 
[Mutlics]: https://en.wikipedia.org/wiki/Multics
[Operating Systems]: http://cs241.cs.illinois.edu/coursebook/index.html
[PDP-7]: https://gunkies.org/wiki/PDP-7
[Unix]: https://www.howtogeek.com/182649/htg-explains-what-is-unix/
