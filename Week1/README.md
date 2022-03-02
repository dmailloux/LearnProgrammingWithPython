# Week 1: Terminal Basics and Python Expressions

Before we get started, note that we will be using the words "folder" and "directory" interchangeably. Same with "terminal" and "PowerShell".

## Terminal Basics

From the Start menu, search for and open Windows PowerShell. You will see something like:

```
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

Try the new cross-platform PowerShell https://aka.ms/pscore6

PS C:\Users\username>_
```

Now, type

```
cd ~/Documents
```

You will now see

```
PS C:\Users\username\Documents>
```

`cd` in PowerShell means "change directory". ~ is shorthand for your home directory, hopefully it is the same for you as it is for me.
Putting it all together, `cd ~/Documents` means "change directory to `home/Documents`". Yes, that `Documents`.

You can see what files and directories are in in the current directory by typing

```
ls
```

Once yo do, you will see a small table like:

| Mode   | LastWriteTime    | Length | Name                   |
| ------ | ---------------- | ------ | ---------------------- |
| d----- | 1/03/22 10:23 PM |        | exampleDirectory       |
| d----- | 3/01/22 5:31 PM  | 41     | exampleFile.txt        |
| d----- | 3/01/22 5:33 PM  |        | someOtherExampleFolder |
| d----- | 2/08/22 1:07 PM  |        | thirdExampleFolder     |

For now, all we care about is what is under the Name heading. These are the names of the files and folders in this directory.

Now type

```
mkdir learnPython
```

`mkdir` makes a new directory. If you type `ls` again, you will now see something like

| Mode   | LastWriteTime    | Length | Name                   |
| ------ | ---------------- | ------ | ---------------------- |
| d----- | 3/01/22 6:04 PM  |        | learnPython            |
| d----- | 1/03/22 10:23 PM |        | exampleDirectory       |
| d----- | 3/01/22 5:31 PM  | 41     | exampleFile.txt        |
| d----- | 3/01/22 5:33 PM  |        | someOtherExampleFolder |
| d----- | 2/08/22 1:07 PM  |        | thirdExampleFolder     |

Now type to change into your newly created directory.

```
cd learnPython
```

You are now in your learnPython directory. Keep this folder around, we are going to be using it for the rest of this tutorial.

## Python Basics

### Expressions

Open up PowerShell if you don't already have it open and enter

```
python
```

You should see something like this

```python
Python 3.10.2 (tags/v3.10.2:a58ebcc, Jan 17 2022, 14:12:15) [MSC v.1929 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> _
```

This is the Python interactive terminal. You can run Python commands one line at a time as shown below. Try it for yourself.

```python
>>> 2 + 2
4
>>> 5 * 5 * -1
-25
>>> 8 / 2
4.0
>>> (4 + 4) / 2
4.0
>>> 4 + 4 / 2
6.0
```

You can see it follows those basic rules of BEDMAS from grade school. It wouldn't be very useful if it did math wrong, but it is good to note.

### Variables

Now we are going to learn about variables. They are the first step on the road to writing any kind of useful program.

```python
>>> a = 2
>>> a
2
>>> b = 3
>>> b
3
>>> a + b
5
>>> a * b
6
>>> c = a + (2 * b)
>>> c
8
```

### Assignment

In Python, `=` is the assignment operator.

```python
>>> a = 3
>>> a
3
>>> b = 4 + 1
>>> b
5
>>> a = b + a
>>> a
8
```

It assigns the value of the expression on its right, to whatever variable is on its left. The expression on the right can even contain the variable on the left. A common use case for this is incrementing a variable.

```python
>>> i = 0
>>> i = i + 1
>>> i
1
>>> i = i + 1
>>> i
2
```

### Types

In order to understand how to perform operations on different variables, programming languages have the concept of _types_.

For example, a number like `1` is considered an **int**, short for **integer**. A number like `1.0` is considered a **float**. Words and letters are of type **string**. The differences between **int** and **float** are subtle, as `1 + 1.0 = 2.0` is not that much of a stretch. However, what would it mean to add `1 + "spaghetti"`? Try it for yourself in the Python interactive terminal and see. (Don't forget the "" around spaghetti).

In short, types affect how expressions are evaluated.

Below is a table of the basic types in Python, along with an example value

| Value              | Type  | Example Expression          |
| ------------------ | ----- | --------------------------- |
| 1                  | int   | 1 + 1 = 2                   |
| 1.0                | float | 1.0 + 1.0 = 2.0             |
| "one"              | str   | "one" + "one" = "oneone"    |
| "1"                | str   | "1" + "1" = "11"            |
| True, False        | bool  | 1 > 2 = False               |
| [2, "hello", True] | list  | len([1, "hello", True]) = 3 |

#### **int (Integer)**

Integers are simple numbers without a decimal component. Nothing to write home about here. You can't divide by 0.

#### **float (Floating Point Number)**

Floats are like integers but with a decimal component. These are probably most like how you think about numbers in your life after grade school. You can't divide by 0.0.

#### **str (String)**

Strings in Python are any sequence of characters, including numbers, enclosed in single quotes or double quotes. `""` and `''` can be used interchangeably, there is no difference. "Hello" means the exact same thing to Python as 'Hello'.

#### **bool (Boolean)**

Booleans are either `True` or `False`. Simple concept, but very powerful in practice. We will go more into this later.

#### **list (List)**

Lists are an ordered collection of values of any type, usually all of the same type, but not always. Lists are declared by placing your values inside of these brackets `[]`. Like booleans, they may seem simple at a glance but they enable some of the really powerful magic of programming. We'll dig way more into these later on.

These are not all the types in Python, but using these types you can write pretty much any program that is possible to write.

### Casting

Let's say you have two variables - a and b.

```python
>>> a = 1
>>> b = "1"
```

Now if you try to add these variables, you will get an error

```python
Traceback (most recent call last):
  File "<pyshell#4>", line 1, in <module>
    a + b
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

To resolve this issue, you can **cast**, one of the variables, let's go with b, so you can perform this operation

```python
>>> b = int(b)
>>> a + b
2
```

When you **cast** a value in Python, you are transforming it explicitly from one type to another.

## Sample Programs

### Hello, World

Open up Visual Studio Code and select `Open Folder` and open up your `~/Documents/learnPython` folder from earlier.

Create a New File called `helloworld.py`.

In that file, write

```python
print("Hello, world!")
```

Open up PowerShell and `cd` to your `~/Documents/learnPython` folder.

Now enter

```
python helloworld.py
```

You should see `Hello, world!` output to the terminal. You have run your first Python program!

### Chef

Now create a new file called `chef.py`, and in it, write the following code.

```python
name = input("What is your name: ")
favourite_food = input("What is your favorite food: ")
print("Hello " + name + ". Here is your " + favourite_food + ".")
```

Now run `chef.py` and see what happens.

## Assignment

Using what you now know, create a new program that will

1. prompt a user for a number
2. then once the user has entered that number, prompt them for another number
3. add those two numbers together and write the result to the terminal

Did something unexpected happen? Why? Review the material in this lesson if you get stuck.

The sample programs can be found under the `Examples` folder up above.
