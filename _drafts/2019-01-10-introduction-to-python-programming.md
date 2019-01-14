---
layout: post
title: "Introduction to Python Programming"
excerpt: Python is a programming language that is both very powerful as well as easy to learn. This post offers a quick introduction to the basic programming constructs in Python.
date: 2019-01-10 09:32:24 +0530
categories: python
---

Python is a programming language that is both very powerful as well as easy to learn. It is focused on code readability, simplicity and expressiveness. Python is the best language to learn while getting started with machine learning. The name Python comes from Monty Python's Flying Circus, a BBC comedy series from the 1970s. Guido van Rossum, the founder of Python, was a fan of this comedy series, and from it, he decided to pick the catchy, unique and slightly mysterious name - Python. This post offers a quick introduction to the basic programming constructs in Python.

This post is focused on Python 3. This is because:
>Python 2 is legacy, Python 3 is the present and future of the language.
>
>-- **Python Wiki**

Before we get started, this post assumes that you are familiar with basic programming constructs like branching, looping, functions, classes and objects and can write code in at least one other programming language.

Like all programming languages, the most effective way to learn Python is by writing its code. It's best if you type out and execute all the code samples in this post.

**Note:** This post does not cover the process of installing Python. However, you *don't* need to have a programming environment set up. You can use Google's Colaboratory to execute all the programs in this post. You can start using it in just 3 simple steps:
- Go to [colab.research.google.com](https://colab.research.google.com/){:target="blank"}.
- Sign in to your Google account.
- Create a new Python 3 notebook.

And voila! You're all set! Check out [this](/media/google-colab.mp4){:target="_blank"} short clip for a demonstration.

# Executing Python Code
For those who are using Google Colaboratory to execute the programs in this post, each snippet of code can be executed using **Shift + Enter**.

And for those who have Python installed locally on your computer, you can execute Python code in two ways.
- **Executing Python scripts:** Python programs can be written using any text editor and saved as a file that ends with a **.py** extension. These scripts can be executed from a shell (Terminal/Command Prompt) using the following command:
{% highlight shell %}
python3 <filename>
{% endhighlight %}
- **Using the interactive mode:** Python, being an interpreted language, has an interactive mode in which we can execute code line by line and see the results of the executed code immediately. To enter the interactive mode, use the following command in a shell:
{% highlight shell %}
python3
{% endhighlight %}

# Diving In
Python is:
- **High level:** Complex problems can be solved in Python using very few lines of code. We don't have to worry about lower level concepts like pointers and memory allocation.
- **Interpreted:** Python programs don't need to be compiled separately before they are executed. While this means that Python runs a little slower than compiled languages like C and Java, it allows Python code to be executed in an interactive mode, which makes debugging very easy.
- **Object oriented:** Like most modern programming languages, Python is an object oriented programming language. It allows us to use concepts like inheritance, polymorphism (and more) to inclucate best practices and to speed up development.
- **Fun:** Ever heard of another programming language that's named after a comedy series?

## Hello, world!
Let's start simple.
{% highlight python linenos %}
print("Hello, world!")
{% endhighlight %}
The `print` function prints "Hello, world!" and a newline (`\n`) character at the end by default. This is unlike lower level languages like C, where the newline character has to be specified explicitly. If you want to replicate C-like behaviour, use:
{% highlight python %}
print("Hello, world!", end="")
{% endhighlight %}
This prints a blank string at the end of "Hello, world!" instead of `\n`. The `end` parameter is a string which is printed at the end of the output string. As you may have guessed, its default value is `\n`.

## Accepting input
Now that we've learnt how to print to the screen, let's accept some input from the user and play around with it a bit.
{% highlight python linenos %}
name = input("Enter your name: ")
print("Hello, {}!".format(name))
{% endhighlight %}

This program highlights a number of features of Python. Let's look at them line by line.

**Line 1:** The `input` function, as the name suggests, allows us to accept input from the user. It also allows us to display a prompt for the user, so that we don't have to write a separate line of code to print that. The value entered by the user is stored in the `name` variable. Notice that we didn't have to specify the data type of the variable. This is because **Python is a dynamically typed language**. A dynamically typed language is one in which the majority of type checking is performed at run-time as opposed to at compile-time. (It's okay if you don't understand what that means. In fact, forget what I just said.) Simply put, we don't have to worry about the data types of variables while initializing them. Python will take care of those for us automagically. This is in contrast to statically typed languages (C, C++, Java), in which we have to specify the data types of variables when they are initialised/declared.

One of the quirks of the `input` function is that it always returns a string. More on this in a minute.

**Line 2:** This line demonstrates a different way of using the `print` function. As mentioned earlier, **Python is an object oriented language**. In Python, all variables are actually objects. `name` is an object of the `str` (string) class. Even `"Hello, {}!"` is an object of the `str` class. These objects have a method called `format` which allows us to inject the values of variables into strings. `{}` is a placeholder, into which the value of a variable is injected. Here, the `name` variable's value in inserted into the string in place of the `{}`, resulting in a string like `"Hello, Andrew!"`. We can also print the values of multiple variables, since the `format` method can take any number of arguments. For instance,
{% highlight python linenos %}
name = "Andrew"
age = 35
print("My name is {} and I am {} years old".format(name, age))
{% endhighlight %}
This snippet of code displays the string "My name is Andrew and I am 35 years old"

**Note:** The syntax for calling the method of an object is the same as it is in other object oriented programming languages like C++ and Java.
{% highlight python %}
object_name.method_name([arguments])
{% endhighlight %}

**Note:** Python often trades off a little flexibility for simplicity. For instance, the `print` function prints a `\n` by default for cleanliness, while allowing the programmer to specify an alternate value for the `end` parameter. Another example is the `input` function, which always returns a string. To accept values of other datatypes, we have to cast the value entered by the user to the required type.

## Arithmetic operations
Python comes with a rich set of arithmetic operations.
{% highlight python linenos %}
x = 10
y = 3
print(x + y)  # Addition
print(x - y)  # Subtraction
print(x * y)  # Multiplication
print(x / y)  # Division
print(x // y) # Integer Division (C-like)
print(x % y)  # Modulus (Remainder)
print(x ** y) # Exponentiation (Power)
# This is a comment, by the way. It starts with a #.

"""
​    While we're speaking about comments,
​    this is a multi-line comment.
​    It starts and ends with a set of three single/double quotes.
"""
{% endhighlight %}

**Lines 1, 2:** These lines simply assign the values 10 to `x` and 3 to `y`.

**Lines 3 - 5:** These lines print the sum (13), difference (7) and product (30) of `x` and `y`. They show another way of using the `print` function.

**Line 6:** Here's where things start to get a little different. This line prints 3.33, unlike languages like C, which print 3. The result of `x/y` is always a floating point number, even when the operands are integers.

**Line 7:** While the `/` operator provides a more intuitive result, integer division, in which the fractional part of the result is truncated off, can be performed by using the `//` operator. This line prints 3.

**Line 8:** The `%` (modulo) operator is used to calculate the remainder after the division of one integer by another. This line prints 1.

**Line 9:** The `**` operator is called the exponentiation/power operator. It is used to calculate \\( x^y \\). This line prints 1000.

To summarise, this is a list of all the **arithmetic operators** available in Python.

| Operator | Name               | Example          |
| -------- | ------------------ | ---------------- |
| `+`      | Addition           | `10 + 3 = 13`    |
| `-`      | Subtraction        | `10 - 3 = 7`     |
| `*`      | Multiplication     | `10 * 3 = 30`    |
| `/`      | Division (Float)   | `10 / 3 = 3.33`  |
| `//`     | Division (Integer) | `10 // 3 = 3`    |
| `%`      | Modulo (Remainder) | `10 % 3 = 1`     |
| `**`     | Exponentiation     | `10 ** 3 = 1000` |

## Compound Interest
Now that we have a basic understanding of how to print to the screen, accept input from the user, and perform basic mathematical operations on data, let's write a program that uses all these concepts to calculate compound interest.

Compound interest is a variant of simple interest, in which the interest earned per year is added to the principal amount, and this amount is used as the principal for the coming year. (More details here: [Compound Interest](https://en.wikipedia.org/wiki/Compound_interest){:target="_blank"})

Given a principal amount \\( P \\), a rate of interest \\( R \\), a time period in years \\( N \\), the amount \\( A \\) that the principal adds up to is given by:

\\[ A = P \times \left(1 + \frac{R}{100} \right)^N \\]

For instance, consider that a principal amount of $10,000 is placed on compound interest for 3 years at a 8% per annum. Using the formula, we can calculate the final amount:

\\[A = 10000 \times \left(1 + \frac{8}{100} \right)^3 \\]
\\[A = $12597.12 \\]

In Python, we can use the inbuilt arithmetic operators to calculate the final amount from the principal amount, rate of interest, and time as follows:
{% highlight python linenos %}
# Accepting principal, rate, and number of years
principal = input("Principal = ")
rate = input("Rate of interest = ")
years = input("Time (in years) = ")

# Casting the input values from strings to floating point numbers
principal = float(principal)
rate = float(rate)
years = float(years)

# Calculating the amount
amount = principal * (1 + rate / 100) ** years

# Printing calculated amount
print("Amount = {}".format(amount))
{% endhighlight %}

**Lines 2 - 4:** These lines are used to accept the values of principal, rate and the number of years from the user. As mentioned earlier, the `input` function always returns a string. To perform mathematical operations on input values, we must first type cast them to a numeric data type, like `int` or `float`.

**Lines 7 - 9:** Here, we type cast the principal, rate and years variables from strings to floating point numbers in order to perform arithmetic operations on them. For those of you who are comfortable with the concepts of object oriented programming, each `str` object is passed to the constructor of the `float` class, which does the necessary conversion and returns a `float` object.

**Shortcut:** We could combine lines 2 - 4 and 7 - 9 by casting the values immediately as they are returned by the `input` function:

{% highlight python %}
principal = float(input("Principal = "))
rate = float(input("Rate of interest = "))
years = float(input("Time (in years) = "))
{% endhighlight %}

**Line 12:** This line calculates the final amount from the formula given above and stores it in the `amount` variable.

**Line 15:** Finally, the calculated amount is displayed on the screen.

## Conditional Branching
Branching is an integral part of any programming language.

### 1. If - Else
{% highlight python linenos %}
year = int(input("Enter the current year: "))

if year % 4 == 0:
​    print("{} is a leap year".format(year))
​    print("{} has 366 days".format(year))
else:
​    print("{} is a leap year".format(year))
​    print("{} has 365 days".format(year))
{% endhighlight %}

Conceptually, there's little to understand in this snippet of code. In involves accepting a year (eg: 2019) from the user and printing whether or not the year is a leap year and the number of days in the year. Syntactically, however, there are a number of things to notice.

**Line 1:** This line accepts the current year from the user.

**Lines 3 - 8:** The main things to notice here are:
- The `==` operator is the **equality operator** and it works just like the equality operator from other programming languages. It compares the values on its left and right sides. The condition results in `True` if the values are equal, and in `False` otherwise.
- Parentheses surrounding the condition are **not required**, unlike in languages like C.
- The condition **must** be followed by a colon (`:`).
- **Indentation.** Python uses indentation instead of braces or keywords as a delimiter for nested blocks of code. An increase in indentation indicates the start of a nested block of code, and a decrease in it indicates the end of that block. The [Python style guide](){:target="blank"} recommends that programmers use 4 spaces of indentation. While this is not compulsory to follow, it is a very good practice.

  >Use 4 spaces per indentation level.
  >
  >Spaces are the preferred indentation method.
  >
  >Tabs should be used solely to remain consistent with code that is already indented with tabs.
  >
  >Python 3 disallows mixing the use of tabs and spaces for indentation.
  >
  >-- Python Style Guide

### 2. If - Else if - Else
Moving forward,
{% highlight python linenos %}
a = int(input("Enter an integer: "))
b = int(input("Enter another integer: "))

if a > b:
​    print("{} is greater".format(a))
elif b > a:
​    print("{} is greater".format(b))
else:
​    print("The numbers are equal")
{% endhighlight %}

**Lines 1, 2:** These lines accept two integers from the user and store them in the `a` and `b` variables respectively.

**Lines 4 - 9:** The key takeaways from these lines are:
- In Python, we use `elif` instead of "else if". `elif` is a Python keyword.
- `>` and `<` are the greater-than and less-than relational operators respectively. Similar to the `==` operator, these behave just like they do in other programming languages.

Following is a list of the **relational operators** available in Python.

| Operator | Name                     | Meaning                                                      |
| -------- | ------------------------ | ------------------------------------------------------------ |
| `==`     | Equal to (Equality)      | True if the left value operand is equal to the right one.    |
| `!=`     | Not equal to             | True if the left operand is not equal to the right one.      |
| `>`      | Greater than             | True if the left operand is greater than the right one.      |
| `<`      | Less than                | True if the left operand is less than the right one.         |
| `>=`     | Greater than or equal to | True if the left operand is greater than or equal to the right one. |
| `<=`     | Less than or equal to    | True if the left operand is less than or equal to the right one. |

The next program is used to check whether a triangle is equilateral (all sides equal), isosceles (any two sides equal) or scalene (all sides unequal).

{% highlight python linenos %}
print("Enter the lengths of the sides of a triangle.")
s1 = float(input("Enter side 1: "))
s2 = float(input("Enter side 2: "))
s3 = float(input("Enter side 3: "))

if s1 == s2 and s2 == s3:               # If all sides are equal
    print("Equilateral triangle")
elif s1 == s2 or s2 == s3 or s3 == s1:  # Else if any two sides are equal
    print("Isosceles triangle")
else:                                   # Else (if all sides are unequal)
    print("Scalene triangle")
{% endhighlight %}

**Lines 2 - 4:** These lines accept the lengths of the sides of a triangle from the user.

**Lines 6 - 11:** The main thing to notice here is the use of `and` and `or` for logically chaining conditions. While other programming languages use symbols like `&&` and `!!` as the logical AND and OR operators, Python uses the English words "and" and "or" in order to improve code readability.

Here's a list of the **logical operators** in Python and their respective counterparts in other programming languages (C, C++, Java)

| Operator | Name        | Operator in C/C++/Java |
| -------- | ----------- | ---------------------- |
| `and`    | Logical AND | `&&`                   |
| `or`     | Logical OR  | `!!`                   |
| `not`    | Logical NOT | `!`                    |

### 3. Switch Case?
Unlike almost every other programming language, Python does not have the switch-case branching construct. This is because we can achieve the equivalent of a switch-case easily by using a sequence of `if... elif... elif... else`.

## Loops
Like branching constructs, loops are an essential part of all programming languages. Python provides the while and for loops.

### 1. While Loop
{% highlight python linenos %}
i = 0
while i < 5:
    print(i)
    i += 1
{% endhighlight %}

Conceptually, this is a simple program. While the condition evaluates to `True`, the indented block of code is executed. The program prints the numbers 0 to 4, one on a line.

**Line 1:** This line initializes an integer variable with a value of 0.

**Lines 2 - 4:** Here, we can syntactic similarities to the if-else constructs.
- Parentheses surrounding the condition are unrequired.
- The condition must be followed by a colon (`:`)
- The indentation rules that govern the if-else constructs are also applicable to while loops.

One additional thing to point out in this program is that Python supports the shortcut operators for combining arithmetic and assignment operators like `+=`, `-=`, etc. All arithmetic operators are supported. However, the increment (`++`) and decrement (`--`) operators from C, C++ and Java are not included in Python.

### 2. For Loop
The for loop in Python is different from the traditional for loop.
{% highlight python linenos %}
for i in range(5):
    print(i)
{% endhighlight %}

{% highlight python linenos %}
for i in range(10, 15):
    print(i)
{% endhighlight %}

{% highlight python linenos %}
for i in range(50, 60, 2):
    print(i)
{% endhighlight %}

{% highlight python linenos %}
for i in range(90, 70, -5):
    print(i)
{% endhighlight %}

### 3. Do-while Loop?
Python doesn't have the do-while loop, as opposed to programming languages like C and C++.

## Lists
An array is a data structure that can store multiple elements (of the same type). In Python, the simplest arrays are called `list`s. However, don't be fooled. A `list` is much more flexible and powerful than a traditional array.

## User Defined Functions
## Python Packages