---
layout: post
title: "Python: Quickstart"
excerpt: Python is a programming language that is both very powerful as well as easy to learn. This post offers a quick introduction to the basic programming constructs in Python.
date: 2019-02-28 21:37:24 +0530
categories: python
---

Python is a programming language that is both very powerful as well as easy to learn. It is focused on code readability, simplicity and expressiveness. Python is the best language to learn while getting started with machine learning. The name Python comes from Monty Python's Flying Circus, a BBC comedy series from the 1970s. Guido van Rossum, the founder of Python, was a fan of this comedy series, and from it, he decided to pick the name - Python. This post offers a quick introduction to the basic programming constructs in Python. Note that this is neither a comprehensive Python tutorial, nor a programming tutorial. This post assumes that you are familiar with basic programming constructs (like branching, looping, functions, classes and objects) and can write code in at least one other programming language. The aim of this post is to get you started with writing Python code quickly.

This post is focused on Python 3. This is because:
>Python 2 is legacy, Python 3 is the present and future of the language.
>
>-- **Python Wiki**

Like all programming languages, the most effective way to learn Python is by writing its code. It's best if you type out and execute all the code samples in this post.

**Note:** This post does not cover the process of installing Python. However, you *don't* need to have a programming environment set up. You can use Google's Colaboratory to execute all the programs in this post. You can start using it in just 3 simple steps:
1. Go to [colab.research.google.com](https://colab.research.google.com/){:target="_blank"}.
2. Sign in to your Google account.
3. Create a new Python 3 notebook.

And voila! You're all set! Check out [this](/media/python-quickstart/google-colab.mp4){:target="_blank"} short clip for a demonstration.

{% include toc %}

# Properties of Python
- **High level:** Complex problems can be solved using very few lines of code.
- **Case sensitive:** `name` and `NAME` are different.
- **Strongly typed:** Data types are enforced. `"Apple" + 2` is not allowed.
- **Dynamically typed:** You don't need to specify the data types of variables while creating them.
- **Interpreted:** Python code can be executed in an interactive mode, which makes debugging very easy.
- **Object oriented:** Everything is an object. Inheritance, polymorphism, etc. are all supported.
- **Clean:** Readability and cleanliness are among the core principles of Python development.
- **Indentation:** Python uses whitespace instead of curly braces or keywords to delimit blocks of code.
- **Fun:** Ever heard of another programming language that's named after a comedy series?

# Executing Python Code
For those who are using Google Colaboratory to execute the programs in this post, each snippet of code can be executed using **Shift + Enter**.

And for those who have Python installed locally on your computer, you can execute Python code in two ways.
- **Executing Python scripts:** Python programs can be written using any text editor and saved as a file that ends with a **.py** extension. These scripts can be executed from a shell (Terminal/Command Prompt) using the following command:
{% highlight shell %}
$ python3 <filename>
{% endhighlight %}
- **Using the interactive mode:** Python, being an interpreted language, has an interactive mode in which we can execute code line by line and see the results of the executed code immediately. To enter the interactive mode, use the following command in a shell:
{% highlight shell %}
$ python3
{% endhighlight %}

# Hello, world!
Let's start simple. Just one line of code. No boilerplate.
{% highlight python linenos %}
print("Hello, world!")
{% endhighlight %}
The `print` function prints "Hello, world!" and a newline (`\n`) character at the end by default. This is unlike lower level languages like C, where the newline character has to be specified explicitly. If you want to replicate C-like behaviour, use:
{% highlight python %}
print("Hello, world!", end="")
{% endhighlight %}
This prints a blank string at the end of "Hello, world!" instead of `\n`. The `end` parameter is a string which is printed at the end of the output string. As you may have guessed, its default value is `\n`.

# Accepting input
Now that we've learnt how to print to the screen, let's accept some input from the user and play around with it a bit.
{% highlight python linenos %}
name = input("Enter your name: ")
print("Hello, {}!".format(name))
{% endhighlight %}

This program highlights a number of features of Python. Let's look at them line by line.

**Line 1:** The `input` function, as the name suggests, allows us to accept input from the user. It also allows us to display a prompt for the user, so that we don't have to write a separate line of code to print that. The value entered by the user is stored in the `name` variable. Note that we didn't have to specify the data type of the variable. This is because **Python is a dynamically typed language**. A dynamically typed language is one in which the majority of type checking is performed at run-time as opposed to at compile-time. (It's okay if you don't understand what that means. In fact, forget what I just said.) Simply put, we don't have to worry about the data types of variables while initialising them. Python will take care of those for us automagically. This is in contrast to statically typed languages (C, C++, Java), in which we have to specify the data types of variables when they are initialised/declared.

One of the quirks of the `input` function is that it always returns a string. More on this in a minute.

**Line 2:** This line demonstrates a different way of using the `print` function. As mentioned earlier, **Python is an object oriented language**. In Python, all variables are actually objects. `name` is an object of the `str` (string) class. Even `"Hello, {}!"` is an object of the `str` class. `str` objects have a method called `format` which allows us to inject the values of variables into strings. `{}` is a placeholder, into which the value of a variable is injected. Here, the `name` variable's value in inserted into the string in place of the `{}`, resulting in a string like `"Hello, Andrew!"`. We can also print the values of multiple variables, since the `format` method can take any number of arguments. For instance,
{% highlight python linenos %}
name = "Andrew"
age = 35
print("My name is {} and I am {} years old".format(name, age))
{% endhighlight %}
This snippet of code displays the string "My name is Andrew and I am 35 years old"

**Note:** The syntax for calling the method of an object is the same as it is in other object oriented programming languages like C++ and Java.
{% highlight python %}
object_name.method_name([args])
{% endhighlight %}

**Note:** Python often trades off a little flexibility for simplicity. For instance, the `print` function prints a `\n` by default for cleanliness, while allowing the programmer to specify an alternate value for the `end` parameter. Another example is the `input` function, which always returns a string. To accept values of other datatypes, we have to cast the value entered by the user to the required type.

# Arithmetic operations
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

# Conditional Branching
Branching is an integral part of any programming language.

## `if..else`
{% highlight python linenos %}
year = int(input("Enter the current year: "))

if year % 4 == 0:
​    print("{} is a leap year".format(year))
​    print("{} has 366 days".format(year))
else:
​    print("{} is not a leap year".format(year))
​    print("{} has 365 days".format(year))
{% endhighlight %}

Logically, this is a simple program. It checks if a year is a leap year. Syntactically, however, there are a number of things to note.

- On line 3, the `==` operator is the **equality operator** and it works just like the equality operator from other programming languages. It compares the values on its left and right sides. The condition results in `True` if the values are equal, and in `False` otherwise.
- On line 3, parentheses surrounding the condition are **not required**, unlike in languages like C.
- On lines 3 and 6, the condition and the `else` keyword **must** be followed by a colon (`:`).
- **Indentation.** Python uses indentation instead of braces or keywords as a delimiter for nested blocks of code. An increase in indentation indicates the start of a nested block of code, and a decrease indicates its end. The [Python style guide](){:target="blank"} recommends that programmers use 4 spaces of indentation.

  >Use 4 spaces per indentation level.
  >
  >Spaces are the preferred indentation method.
  >
  >Tabs should be used solely to remain consistent with code that is already indented with tabs.
  >
  >Python 3 disallows mixing the use of tabs and spaces for indentation.
  >
  >-- Python Style Guide

**Note:** In Python, the boolean values are `True`/`False` (case sensitive) as opposed to `true`/`false` (in C++, Java, JavaScript, etc.) or `0`/`1` (in C).

## `if..elif..else`
Moving forward..

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

**Lines 4 - 9:** These lines compare the values of `a` and `b` and print either the larger value or that the numbers are equal. The key takeaways from these lines are:
- In Python, we use `elif` instead of "else if". `elif` is a Python keyword.
- `>` and `<` are the greater-than and less-than relational operators respectively. Similar to the `==` operator, these behave just like they do in other programming languages.

Following is a list of the **relational operators** available in Python.

| Operator | Name                     | Meaning                                                      |
| -------- | ------------------------ | ------------------------------------------------------------ |
| `==`     | Equal to (Equality)      | True if the left operand is equal to the right one.    |
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

## Nested `if..else..`
As mentioned earlier, an increase in the level of indentation marks the start of a new block of code and a decrease marks its end. Following that, an `if..else` block can be nested inside another simply by adjusting the indent level to demarcate the start and end of the nested block.

{% highlight python linenos %}
marks = int(input("Enter your marks: "))
if marks >= 40:
    print("Well done!")
    print("Your grade is: ", end="")
    if marks > 80:
        print("Outstanding")
    else:
        print("Good")
else:
    print("Don't give up! You can do better.")
{% endhighlight %}

Yikes! It's exam time. This program takes the user's marks as input and tells the user how well he's done. If the user has scored over 40 marks, he is also given a grade: "Outstanding" if his marks are over 80, and "Good" otherwise. Note that after line 8, the indent reduces by two levels. This indicates the end of both the nested `else` block as well as the outer `if` block.

## `switch case`?
Unlike almost every other programming language, Python does not have the switch-case branching construct. This is because we can achieve the equivalent of a switch-case easily by using a sequence of `if..elif..elif..else`.

# Lists
An array, as we know, is a simple data structure that can store multiple elements of the same type. In Python, arrays are called `list`s, and their powerful & flexible constitution gives programmers a very hassle-free experience. The drudgery of resizing an array each time we need to add or remove elements is gone! **The length of a `list` is dynamic, and a `list` can store elements of different data types.**  Python lists are **0-indexed**, i.e. the index of the first element in a `list` is 0.

## Creating a `list`

Since Python lists are objects of the `list` class, we can create an empty `list` by calling its constructor.
{% highlight python linenos %}
l = list()
{% endhighlight %}
**Note:** The syntax for creating an object of a class is:
{% highlight python %}
object_name = ClassName([args])
{% endhighlight %}

Python also provides a shortcut syntax for creating a `list`.
{% highlight python linenos %}
l = []  # Equivalent to: l = list()
{% endhighlight %}

The syntax for initialising a non-empty `list` is quite similar to the shortcut notation. Elements are separated by commas (`,`).
{% highlight python linenos %}
prime_numbers = [2, 3, 5, 7, 11]
{% endhighlight %}

As mentioned earlier, a `list` can contain elements of different data types. A `list` can even contain another `list`. Once again, elements are comma-separated.
{% highlight python linenos %}
odd_numbers = ['one', 3, 5, 'seven', [9, 11], 13]
{% endhighlight %}

## Accessing elements of a `list`
An element of a `list` can be accessed by using its index.
{% highlight python linenos %}
languages = ['Python', 'C', 'C++', 'Java', 'Swift', 'PHP']
print(languages[0])   # Prints Python
print(languages[1])   # Prints C

print(languages[-1])  # Prints PHP
print(languages[-2])  # Prints Swift
{% endhighlight %}

**Line 1:** This line creates a `list` of 6 strings.

**Line 2:** Here, we print the 1st element of `languages` (the string which is present at the 0th index).

**Line 3:** This line prints the 2nd element of `languages` (the string which is present at index 1).

**Line 5:** This line shows us a nifty way of accessing the last element of a `list`. While the last element of the `languages` list could be accessed as `languages[5]`, being able to use `languages[-1]` is a handy feature as it allows us to access the last element of any `list` without us having to know its length.

**Line 6:** Not only can we access the last element of a `list` by using the `-1` index, but we can also access the second last (and third last, fourth last, etc.) element by using the `-2` (and `-3`, `-4`, etc.) index. This line prints the second last element of the `list`.

The following image is helpful in understanding the way positive and negative indices work in Python. The first row of indices shows the actual indices of the elements and the second row of indices shows the corresponding negative indices.

![Python Indices](/media/python-quickstart/python-indices.png)
*List indices in Python*
<!-- <p style="text-align:center;text-decoration: underline;">Fig. 1 - List indices in Python</p> -->

## Slicing a `list`
In addition to accessing individual elements of a list, Python also allows us to access multiple elements of a `list` (which are called slices of the `list`). Imagine taking a `list` and cutting (slicing) out a section of it. This is exactly how slicing works. **It does not affect the original `list`**, but allows us to extract a slice of the `list`.

{% highlight python linenos %}
even_numbers = [2, 4, 6, 8, 10]

first_three = even_numbers[0:3]
print(first_three)

mid_num = even_numbers[2:3]
print(mid_num)

alternate = even_numbers[0:5:2]
print(alternate)

# Negative indices work too!
last_two = even_numbers[-2:]
print(last_two)
{% endhighlight %}

**Line 1:** We start by creating a `list` of the first 5 even numbers.

**Lines 3, 4:** Here, we slice out the first three elements of the `even_numbers` list and print them. The syntax is:
{% highlight python %}
list_name[<start index>:<end index>]
{% endhighlight %}
All elements from the starting index (inclusive) to the ending index (exclusive) are extracted. That is, if the start and end indices are 0 and 3 respectively, the elements at the indices 0, 1 and 2 will be extracted.

**Shortcut:** If the starting index is not specified, all elements from the start of the `list` up to the specified ending index are extracted.
{% highlight python %}
first_three = even_numbers[:3]  # Equivalent to: even_numbers[0:3]
{% endhighlight %}
Similarly, if the ending index is not specified, all the elements in the `list` from the starting index right up to the end of the `list` are extracted.
{% highlight python %}
last_three = even_numbers[3:]  # Equivalent to: even_numbers[3:5]
{% endhighlight %}

**Lines 6, 7:** Here, we pull out the middle (3rd) element from the `even_numbers` list and print it. The starting index is 2 and the ending index is 3. Hence, the only extracted element is the one present at index 2.

**Note:** Slicing a `list` results in another `list`, even if the resulting sliced `list` has only one element (or even zero elements) in it.

**Lines 9, 10:** These lines show that we can also slice out elements that are not consecutive to each other by specifying the step amount. The step refers to the amount incremented after each index. The syntax for providing a step amount is:
{% highlight python %}
list_name[<start index>:<end index>:<step>]
{% endhighlight %}
On line 9, we specify starting and ending indices as 0 and 5 respectively and a step of 2. This extracts the elements at the indices 0, 2, 4 from `even_numbers` and stores them in `alternate`. The step amount can also be a negative number.

{% highlight python %}
print(even_numbers[4:0:-2])  # Extracts elements at indices 4, 2.
{% endhighlight %}

**Note:** When unspecified, the step amount defaults to 1.

**Lines 13, 14:** Negative indices work the same way in slicing as they did in accessing individual elements. Here, the starting index provided is -2, which points to the second last element of the `list`, and the ending index is unspecified. Hence, all elements from the second last element to the end of the `list` are extracted.

## Playing around with a `list`
Let's get acquainted with some useful functionality the `list` class offers.

{% highlight python linenos %}
# Create a list
names = ['Hinton', 'Le Cun', 'Benjio']

# Add an element to the list
names.append('Karpathy')
# 'Karpathy' is added to the end of the list.
# The list is resized automagically.
print(names)
# Prints ['Hinton', 'Le Cun', 'Benjio', 'Karpathy']

# Append multiple names to the list
names += ['Trask', 'Ng']
# The names are added to the end of the list.
print(names)
# Prints ['Hinton', 'Le Cun', 'Benjio', 'Karpathy', 'Trask', 'Ng']

# Insert an element at a particular index
names.insert(3, 'Dean')
# 'Dean' is inserted at index 3 of the list.
# The elements from index 3 to the end of the list are all pushed forward.
print(names)
# Prints ['Hinton', 'Le Cun', 'Benjio', 'Dean', 'Karpathy', 'Trask', 'Ng']

# Remove an element
names.remove('Karpathy')
# 'Karpathy' is removed from the list.
# If there were multiple instances of 'Karpathy' in the list,
# only the first one would get removed.
print(names)
# Prints ['Hinton', 'Le Cun', 'Benjio', 'Dean', 'Trask', 'Ng']

# Remove an element at a particular index
names.pop(2)
# 'Benjio' - the element at index 2 - is removed.
print(names)
# Prints ['Hinton', 'Le Cun', 'Dean', 'Trask', 'Ng']

# Remove the last element
names.pop()
# 'Ng' - the last element in the list - is removed.
print(names)
# Prints ['Hinton', 'Le Cun', 'Dean', 'Trask']

# Sort the list
names.sort()
# The list is sorted in alphabetical order.
# A list of numbers would get sorted in ascending order.
# To sort in descending (reverse alphabetical) order, use:
# names.sort(reverse=True)
print(names)
# Prints ['Dean', 'Hinton', 'Le Cun', 'Trask']
{% endhighlight %}

# Loops
Like branching constructs, loops are an essential part of all programming languages. Python provides the `while` and `for` loops.

## `while` Loop
{% highlight python linenos %}
i = 0
while i < 5:
    print(i)
    i += 1  # Equivalent to: i = i + 1
{% endhighlight %}

This program prints the numbers 0 to 4, one on a line. While the condition evaluates to `True`, the indented block of code is executed.

**Lines 2 - 4:** Here, we can see syntactic similarities to the `if..else` constructs.
- Parentheses surrounding the condition are not required.
- The condition must be followed by a colon.
- The indentation rules that govern the `if..else` constructs are also applicable to `while` loops.

One additional thing to point out in this program is that Python provides the shortcut operators (`+=`, `-=`, etc.), for combining arithmetic and assignment operations. Shortcut operators for all arithmetic operations are provided (even `//=` and `**=`). However, the increment (`++`) and decrement (`--`) operators from C, C++ and Java are not included in Python.

## `for` Loop
The `for` loop in Python is different from the traditional `for` loop. The syntax is:
{% highlight python %}
for <placeholder> in <iterable>:  # For now, think of an iterable as a list.
    <do some stuff>
{% endhighlight %}
Once again, we can see some syntactic similarities here with the `if..else` constructs and `while` loops, such as the colon after the iterable and the indentation to delimit blocks. `for` and `in` are Python keywords.

**Note:** Python lists and iterables are fundamentally different in their implementation. However, at this point, it helps to think of an iterable as a `list` in order to gain a conceptual understanding of how `for` loops work.

With each iteration of the loop, the next value in the iterable is stored in the placeholder. Note that **the indices of the values are not stored in the placeholder. The values themselves are stored.**

{% highlight python linenos %}
numbers = [9, 3, 6, 5, 2, 7]
for i in numbers:
    print(i)
{% endhighlight %}

This snippet prints the elements in `numbers` line by line. With each iteration of the `for` loop, the next element in `numbers` (iterable) is stored in `i` (placeholder) and is subsequently printed.

{% highlight python linenos %}
for i in range(0, 10, 2):
    print(i)
{% endhighlight %}

`range()` is a Python function that creates and returns an iterable (once again, think of an iterable as a `list` for now). It takes three parameters, a start index (inclusive), and end index (exclusive) and a step amount. These parameters work exactly like the start index, end index and step from `list` slicing. In the above snippet, `range(0, 10, 2)` creates an iterable of the numbers 0, 2, 4, 6, 8. The `for` loop places these numbers one by one in `i` and they are then printed.

Negative step amounts are also allowed.
{% highlight python linenos %}
for i in range(90, 70, -5):
    print(i)
{% endhighlight %}
`range(90, 70, -5)` creates an iterable of the numbers 90, 85, 70, 75. The `for` loop iterates over this iterable and prints the numbers in it.

The step parameter is optional. When left unspecified, it defaults to 1.
{% highlight python linenos %}
for i in range(10, 15):
    print(i)
{% endhighlight %}
This snippet prints the numbers 10 to 14, one on each line.

When the `range` function is passed only one parameter, it is treated as the stop parameter. In that case, the start parameter defaults to 0 (and the step parameter defaults to 1).
{% highlight python linenos %}
for i in range(5):
    print(i)
{% endhighlight %}
Here, `range(5)` creates an iterable of the numbers 0, 1, 2, 3, 4, and the `for` loop iterates over it and prints all the numbers in it.

## `do-while` Loop?
Python doesn't have the do-while loop, as opposed to programming languages like C and C++.

# User Defined Functions
We've used predefined functions like `print`, `input` and `range`. Now, we'll start writing our own reusable functions.

For starters, let's write a function that accepts a positive integer from the user.

{% highlight python linenos %}
def get_positive_int():
    num = 0
    while num <= 0:
        num = int(input("Enter a positive integer: "))
    return num

x = get_positive_int()
print("You entered:", x)
{% endhighlight %}
**Line 1:** A function definition starts with the `def` keyword and is followed by the function name, parentheses and a colon.

**Lines 2-5:** Similar to the `if..else` constructs and the loops, indentation is used to indicate the start and end of the function's body. The return value of a function is specified using the `return` keyword. Note that we **don't** need to specify the return type of the 

**A function can be called only after it is defined.**

Next, let's write a function to calculate the area of a rectangle.

{% highlight python linenos %}
def area(length, breadth):
    return length * breadth

l = float(input("Length: "))
b = float(input("Breadth: "))

print("Area =", area(l, b))
print("Area =", area(length=l, breadth=b))
print("Area =", area(breadth=b, length=l))
{% endhighlight %}

**Lines 1, 2:** The `area` function accepts two parameters: `length` and `breadth` and returns their product.

**Lines 7 - 9:** These lines show different ways of specifying the parameter values to a function. Semantically, these lines are all equivalent.
- The parameters can be passed as simple positional parameters. `l` and `b` correspond to the first and second parameters of the function, i.e. `length` and `breadth`.
- The parameters can also be passed as keyword parameters. Here, `length` is explicitly set to `l` and `breadth` is explicitly set to `b`.
- When the parameters are passed as keyword parameters, they may be passed in any order without any errors.

Finally, let's modify the `get_positive_int()` function to make it more flexible. We'll allow the programmer to pass a prompt message as a parameter. If the message is not passed, a standard prompt message will be used as default.
{% highlight python linenos %}
def get_positive_int(prompt="Enter a positive integer: "):
    num = 0
    while num <= 0:
        num = int(input(prompt))
    return num

age = get_positive_int("Enter your age (in years): ")
x = get_positive_int()
{% endhighlight %}

**Line 1:** Here, we provide a default value for the `prompt` parameter while defining the function.

**Line 7:** While calling the function, when a value is provided for the `prompt` parameter, that value is used.

**Line 8:** However, when no value is passed, the default value we assigned on 
line 1 is used.

**Note:** Functions don't necessarily have to return a value. However, a function that doesn't return anything explicitly actually returns a special value called `None`.

# Modules and Packages
Python comes with a lot of functionality right out of the box. Much of this comes from the rich set of built-in modules and packages that are part of the [Python Standard Library](https://docs.python.org/3/library/). These offer a wide variety of functionality, ranging from general operating system services through Internet data handling and networking to cryptographic functions and database APIs.

Simply put, a **module** is a file containing Python code (e.g any_file.py). And a **package** is a directory containing many such modules (generally grouped logically). For a directory to be treated as a package, it must contain a file named `__init__.py`.

## Importing modules/packages
To avail the functionality, the respective module/package must be imported. Consider the following example.
{% highlight python linenos %}
import time

print("Counting to 5...")
for i in range(1, 6):
    print(i)
    time.sleep(1)
{% endhighlight %}

**Line 1:** We start by importing the `time` module, which contains the definitions of a number of useful time-related variables and functions. It is a part of the Python Standard Library.

**Lines 3 - 6:** Having imported the `time` module, all its functions and variables are now available for use. Note how the `sleep` function of the `time` module is invoked to pause the program for 1 second after each count.

An alternate way of importing is..
{% highlight python linenos %}
from time import sleep

print("Counting to 5...")
for i in range(1, 6):
    print(i)
    sleep(1)
{% endhighlight %}

**Line 1:** Here, we import only the `sleep` function from the `time` module.

**Line 6:** Now, we can directly call the `sleep` function without prefixing it with the name of the `time` module.

## Installing packages
In addition to the packages that come with the Python Standard Library, we can easily download and install packages that are available from the [Python Package Index (PyPI)](https://pypi.org). One such package is [matplotlib](https://matplotlib.org). It is used for creating graphs and charts. We can download and install it with a single shell command.
{% highlight shell %}
$ pip3 install matplotlib
{% endhighlight %}

**Note for Colab users:** Shell commands can be run from within a colab environment by prefixing the command with an exclamation mark (`!`).

{% highlight shell %}
!pip3 install matplotlib
{% endhighlight %}

## Back to importing
Now that we've installed matplotlib, let's import it and use it to create a line graph.

{% highlight python linenos %}
import matplotlib.pyplot as plt

x_axis = [0, 1, 2, 3, 4]
y_axis = [3, 5, 4, 1, 7]

plt.plot(x_axis, y_axis)
plt.show()
{% endhighlight %}

**Line 1:** The matplotlib package is a collection of many modules. Here, we import the pyplot module from it. Also, we tell the interpreter that we'll refer to this module using the short name `plt` instead of the unwieldy `matplotlib.pyplot`.

**Lines 3, 4:** Next, we create two lists, `x_axis` and `y_axis`, which hold the values that are plotted on the \\( x \\) and \\( y \\) axes respectively.

**Line 6:** We create the plot using the `plot` function, which is defined in the pyplot module. To access it, we have to prefix it with `plt` (and not `matplotlib.pyplot`). The `plot` function accepts two lists and creates a line graph using them.

**Line 7:** The `show` function displays the created plot. Ta da!

![Line Graph](/media/python-quickstart/line-graph.png)

-----

And with that, we've reached the end of this post.

# Epilogue
I hope you are now comfortable with the basic concepts of Python programming and that you feel confident about writing your own Python programs. Learning to code in Python has opened up a world of possibilities for you! Here are some of the many paths you can follow..
- Machine Learning, Deep Learning, Artificial Intelligence
    + [NumPy tutorial](http://cs231n.github.io/python-numpy-tutorial/#numpy)
    + [Intro to Machine Learning](https://www.udacity.com/course/intro-to-machine-learning--ud120)
    + [Deep Learning Specialization](https://www.coursera.org/specializations/deep-learning)
    + [fast.ai](https://course.fast.ai)
    + This blog! Currently in its infancy, but I'm going to be posting a lot of ML content.
- Web Development
    + [Django](https://www.djangoproject.com) (Instagram uses this!)
    + [Flask](http://flask.pocoo.org)
- GUI Development
    + [Tkinter](https://docs.python.org/3.7/library/tkinter.html)
- Game Development
    + [PyGame](http://inventwithpython.com/pygame/)

Happy Journey!
