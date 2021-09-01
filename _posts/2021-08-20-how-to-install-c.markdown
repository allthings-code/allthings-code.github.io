---
layout: post
title:  "How to Install C"
series: "I C What You Did There"
date:   2021-08-20 23:32:43 -0700
published: true
categories:
---

“But it works on my machine” -- Unknown

# Prerequisites
[History of C][History of C]

# Introduction
Sally sells C shells on the C shore. Okay, not really. But, she might help us install C with a shell (wink wink). Let's discuss how to install C so we can get to coding!

# Install an IDE
Now, the choice of IDE (Integrated Development Environment - a fancy word for code editor) for every developer is a sacred one. Choose whichever suits your coding style. I love using Visual Studio Code and will use it throughout this series. To install, select the version for your operating system here: [Visual Studio Code Installation][Visual Studio Code].

# Install C on Windows
First thing we need to do is install Mingw. It's a Windows port of the GNU Compiler Collection [GCC][GCC], a set of compilation tools to turn our C code into machine code. To get started, install here [mingGW Installation][minGW]. Once downloaded, open the file to begin start up.

Follow installation defaults until you are presented with the minGW Installation Manager. Here you must additionally select Mingw32-base package and Ming32-gcc-g++ package to be installed.

Once installed, we need to set the path environment variable to reference MinGW. From the Windows start menu, go to view advanced system settings -> environment variables. Find the 'path' variable and hit edit -> new. Here you'll need to add the path to the MinGW folder. It's most likely, C:\MinGW\bin.

# Install C on macOS
First thing we need to do is open a terminal. This can be done by searching 'terminal' on the launchpad. Once opened, type 'gcc' into the terminal. Assuming it is not installed, you will be prompted to install the required tools. And you are all done!

# Install C on Linux
Every Linux distro is a tad differnt, but I will assume you're using Ubuntu. If not, please leave a comment and I will happily update the blog to reference your distro. 

First thing we need to do is open a terminal and once opened, run:

{% highlight c %}
sudo apt install build-essential
{% endhighlight %}

This will install build-essential, a package of tools including those required to run C.

# Verify Success
To ensure we've installed all the tools we need successfully, open a terminal. Windows users can do this by searching for 'command prompt' from the start menu. Once opened, simply type and run the command: {% highlight c %} gcc --version {% endhighlight %}
 
 If the output is some version of gcc and not a red, screaming error then you all done! Yay, congratualtions. If you do see the error, then straight to jail!

# Install VSCode C/C++ Extension
Now, we need our IDE to support C. In the case of VSCode, all we need to do is install the 'C/C++ for Visual Studio Code' by Microsoft extension. The extension store can be found by hitting Ctrl+shift+X after launching VSCode.

# Hello World
To reallllly verfy success we need to code something in C! What's better than the pinical of programming tutorials, the Hello World program.

Assuming you're using VSCode, launch the application. Click File -> New File. This will be our workspace for the time being. Click File -> Save As and save your file to your machine. I'll go ahead and name my file helloworld and set the 'file type' to C.

Once our file is all set up, copy and paste in the following code into your file. Remember to save your changes to the file.

{% highlight c %}
#include <stdio.h>

int main() {
   printf("Hello World!");
   return 0;
}
{% endhighlight %}

So what in the heck is going on here?
The first line, headed with {% highlight c %} #include <stdio.h> {% endhighlight %} is telling our compiler, 'Hey, I need to do some printing of text in a bit. Let me use the standard input and output (stdio) functions to do that".

Next we see an {% highlight c %} int main() {% endhighlight %}. This line is defining the main function. We can execute code that resides within functions. The main() function is special in that it is the starting point of our program. The int part tells us that main() returns an integer upon completion. This integer can tell users whether or not main() finished succesfully.

Then we see, {% highlight c %} printf("Hello World!") {% endhighlight %}. Remember earlier when we included stdio? Now, we are using a function within that stdio library, printf(). Printf() will print the contents passed to it to the command prompt.

Finally, we see a {% highlight c %} return 0 {% endhighlight %}. This is returning the int laid out before our main() function definition. 0 actually defines success and anyone observing the output of main() will know our print functionality was a glorious success. In other scenarios one might return -1 if printf() failed to work.

# Compile and Run Your First C Program
Now that we understand what our code does, let's compile and run it using the tools we installed earlier. From within VSCode, select the 'terminal' button near the top of the page. This will open a terminal within the VSCode editor. If you prefer to use a different terminal, that's fine to. Just make sure you work in the same location as your helloworld.c file.

Now, from your terminal, run the command:

{% highlight c %}
gcc <your-file-name>.c -o HelloWorld#include <stdio.h>
{% endhighlight %}

 This command will use gcc to compile your .c file into a HelloWorld executable. This executable will run our code in main()!

Next, run the command:

{% highlight c %}
./HelloWorld
{% endhighlight %}

You should see the following written to you:

{% highlight c %}
Hello World!
{% endhighlight %}

Congratulations on your successful C program! 

# Read Next
[C Fundamentals][C Fundamentals]

# Appendix
- [More on GCC][GCC]
- [MinGW Documentation][MinGW Documentation]
- [Visual Studio Code Documentation][Visual Studio Code Documentation]

[C Fundamentals]: https://google.com
[History of C]: https://google.com
[MinGW Documentation]: https://www.mingw-w64.org/
[MinGW Installation]: https://sourceforge.net/projects/mingw/
[More on GCC]: https://en.wikipedia.org/wiki/GNU_Compiler_Collection
[Visual Studio Code]: https://code.visualstudio.com/download
[Visual Studio Code Documentation]: https://code.visualstudio.com/docs
