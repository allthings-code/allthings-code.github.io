---
layout: post
title:  "C Fundamentals Part 1 - Data types"
series: "I C What You Did There"
date:   2021-09-01 22:32:43 -0700
published: true
categories: jekyll update
---

"When I was young, I had to learn the fundamentals of basketball. You can have all the physical ability in the world, but you still have to know the fundamentalsYou can't trust code that you did not totally create yourself." - Michael Jordan

# Prerequisites
- [A Brief History of C the Language][A Brief History of C the Language]
- [How to Install C][How to Install C]

# Introduction
Now that we've got things installed and working on our computer, let's get into learning the fundamentals of C! The fundamentals made Jordan the greatest basketball player of all time and learning the basics of C will make you the greatest programmer of all time (after myself of course). We will start with learning about data types.

# Data Types
You can think of data types as the building block of any program. If I want to design a calculator, I need somewhere to store the user's input numbers. If I create an online calendar, I need somewhere to store the names of events. C has many data types for many occassion, but we will discuss and practice using these 4: char, int, double, and char*.

# Char
The char, pronounced like the char in char-grilled mmmm, is a fundamental C data type. It is used to store and represent exactly one [byte][byte] (8 bits) of data. It is most often used to represent single characters of the alphabet or small integers. Here's an example of defining and storing a value in a char.

{% highlight c %}
#include <stdio.h>

int main() {
   char a = 'a';
   char A = 'A';
   char bananas = 'b';
   char sea = 'c';
   printf("%c, %c, %c", a, bananas, sea);
   return 0;
}
{% endhighlight %}

In this preceding example, we define and set the value for 4 different variables: a, A, bananas, and sea. To do this we inform the compiler of the type of our data, in this case: char. Then we give our variable a name. This can be anything and should be something useful (that's why I went with bananas). Once a name has been given, we give our variable a value. For setting the value of a char, notice we must use '' single quotes. These are designated specifically for the use of chars. If you run this small little program, you should see the following output:

{% highlight c %}
a, b, c
{% endhighlight %}

This, if you recall from our installing C post, is being done by the printf() function. Printf() is unique in that it can take in special formatting instructions. %c tells printf to expect a char.

Let's code up another char example.

{% highlight c %}
#include <stdio.h>
#include <ctype.h>

char customCaser(char input) {

   char output = 'x';
   if (islower(input)) {
      output = toupper(input);
   }

   if (isupper(input)) {
      output = toupper(input);
   }

   return output;
}

int main() {
   char a = 'a';
   char A = 'A';
   char bananas = 'b';
   char sea = 'c';

   bananas = customCaser(bananas);
   A = customCaser(A);

   printf("%c, %c, %c, %c", a, bananas, sea, A);
   return 0;
}
{% endhighlight %}

This one is a lot, so take sometime to read it thoroughly. Here we define a new function, called customCaser. Now, customCaser's job is to invert the case of any character it recieves. If it sees an A, it will return a. If it sees z, it will return Z. To accomplish this, customCaser is using a series of if {} statements. If statements tell the C compiler to only do what is inside the {} brackets **if** the statement inside the () is true. So, if our input is lowercase, make it uppercase and vice versa.

To actually do the checking of case, we are using library function written by someone else defined in [\<ctype.h\>][<ctype.h>]. Just like when we included \<stdio.h\> to get access to printing functionalty, we must do the same to get access to assorted case functions. We use four: islower, toupper, isupper, and tolower. The functions prefixed with is simply return true or false for use in our if statments. Those prefixed with to actually do the case change. Their output is stored in our output variable and returned from the customerCaser function.

# Int
Int, pronounced like the int in integer...how boring, is the most common C data type. It, like the name implies, holds integer data. Defining an int is much like defining a char. First we outline the type, give our variable a name, and finally a value.

{% highlight c %}
int numberOfBalloons = 7;
{% endhighlight %}

Let's actually use ints to create a simple calculator.

{% highlight c %}
#include <stdio.h>

int subtract(int a, int b) {
	return a - b;
}

int add(int a, int b) {
	return a + b;
}

int main() {
   int seven = 7;
   int three = 3;
   int ten = add(seven, three);
   int four = subtract(subtract(ten, three), three);
   printf("\n%d", four);
   return 0;
}
{% endhighlight %}

In this calculator example, we define two functions outside of main: add and subtract. As you might've guess, add takes in two inputs and returns their addition. To accomplish this, we use the '+' C operator. We will cover operators more later. Subtract also takes in two inouts, but returns their subtraction instead.

In main, we define four new variables using the int data type. To give the variable four its' value, we actually nest two calls to the subtract method. The first call actually becomes the input to the second call!

We print our output, but now use the %d formatter so printf knows we are printing ints and not chars. The \n is not necessary. It simply declutters the output by including a new, empty line before we print.

# Double
Doubles are extremely similar to ints, but can actually represent decimal values like 8.0, 44.44, or 100.31. This is useful when we require more granularity. Let's get right into an example.


{% highlight c %}
#include <stdio.h>

double toCelsius(double fahrenheit) {
	return ((fahrenheit - 32) / 1.8);
}

int main() {
   double roomTemp = 72.0;
   double fever = 101.0;

   printf("\n%f, %f", toCelsius(roomTemp), toCelsius(fever));
   return 0;
}
{% endhighlight %}

Which results in:

{% highlight c %}
22.222222, 38.333333
{% endhighlight %}

In this printf statement we use %f to designate us printing doubles to console.

If we used ints in place of the double inputs, we would get these results instead:

{% highlight c %}
22, 38
{% endhighlight %}

You can see, we lose a lot of granularity. In cases were the decimal value is important, we need to use doubles.

# Char*
Pronounced char pointer, char star, or string. Char* is used to represent more than one character. Wihtout char\*, storing a name would mean defining a character for every letter ourselves. That would put everyone off of learning C. Instead, we let the compiler do that for us by defining a char*. 

{% highlight c %}
#include <stdio.h>
#include <string.h>

int main() {
   char* hello = "hello";
   char* space = " ";
   char* world = "world";
   int allTogether = strlen(hello) + strlen(space) + strlen(world);
   printf("\n%s + %s + %s makes: %d characters", hello, space, world, allTogether);
   return 0;
}
{% endhighlight %}

{% highlight c %}
hello +   + world makes: 11 characters
{% endhighlight %}

Here, we define three new char* variables. Notice we use "" instead of '' that are reserved for chars. We also define an int to store the output of the addition of 3 calls to strlen(). Now, strlen is actually defined in [\<string.h\>][<string.h>] and calculates the length of a string. The string "bananas" would return 7 when used within strlen. 

Our printf function now uses %s to mark our use of char\*.

# Read Next
WIP

# Appendix
- [Byte][Byte]
- [\<ctype.h\>][<ctype.h>]
- [\<string.h\>][<string.h>]

[A Brief History of C the Language]: https://allthings-code.github.io/2021/08/18/history-of-c.html
[Byte]: https://en.wikipedia.org/wiki/Byte
[<ctype.h>]: https://www.tutorialspoint.com/c_standard_library/ctype_h.htm
[How to Install C]: https://allthings-code.github.io/2021/08/20/how-to-install-c.html
[<string.h>]: https://www.techonthenet.com/c_language/standard_library_functions/string_h/index.php