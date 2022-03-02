# Lesson 2: Boolean Logic and Conditionals

## Boolean Values

Quick reminder from lesson 1, booleans are either True or False. They are most commonly found as the result of some expression evaluating, usually to control the flow of a program. Let's get into what that means.

## Boolean Operators

Python has operators that allow you to perform logic with boolean values. Anyone who has worked with logic before will find them very familiar.

| Operator | Example        | Result |
| -------- | -------------- | ------ |
| and      | True and False | False  |
| or       | True or False  | True   |
| not      | not True       | False  |

### Comparison

Python also has operators that allow you to compare (usually non-boolean) values. These operators always cause an expression to evaluate to a boolean.

| Operator | Example | How to Read Example           | Result |
| -------- | ------- | ----------------------------- | ------ |
| <        | 1 < 1   | 1 less than 1?                | False  |
| <=       | 1 <= 1  | 1 less than or equal to 1?    | True   |
| >        | 1 > 3   | 1 greater than 3?             | False  |
| >=       | 1 >= 3  | 1 greater than or equal to 3? | False  |
| !=       | 1 != 1  | 1 does not equal 1?           | False  |
| !=       | 1 == 1  | 1 equals 1?                   | True   |

These comparison operators work for most of the simple types in Python, but the results can be strange for things other than numbers and strings. Strings are compared alphabetically in a way that feels intuitive.

```python
"a" < "b"
True
"aa" < "b"
True
"bark" < "barf"
False
```

**NOTE:**

- `a == b` checks if `a` is equal to `b`
- `a = b` sets `a` to be equal to `b`

This is a very common source of confusion for beginners.

## Conditionals

### if, elif, and else Statements

Using the new comparison operators we have just learned, we can write our first `if` statement.

```python
x = 3
if x == 3:
    print("That's it!")
```

This program will print "That's it!"

```python
x = 3
if x != 3:
    print("That's it!")
```

This program will not print anything.

```python
x = 10
if x < 3:
    print("One")
elif x < 5:
    print("Two")
elif x < 9:
    print("Three")
elif x < 11:
    print("Four")
```

This program will print "Four"

```python
x = 10
y = "Default"

if x < 3:
    y = "One"
elif x < 5:
    y = "Two"
else:
    y = "Infinity"

print(y)
```

And this program will print "Infinity".

### Nesting

Now that we've had our fun, we have to learn about nesting. All, or at least most programming languages have the concept of nesting, but in Python it takes the form of "meaningful white space". What that means for us, is the indentation of our program will affect how it behaves. This is actually relatively uncommon among programming languages, but it's meaning should become clear with some examples.

```python
x = 5
y = 2
if x > y:
    print("hello")
    y = 5
    if x == y:
        print("goodbye")
else:
    x = 3
y = 4

print("x ==", x)
print("y ==", y)
```

What do you think this program will print?

It turns out the answer is

> hello
>
> goodbye
>
> x == 5
>
> y == 4

Why is that?

It has to do with nesting.

First, because x is greater than y, we print "hello".

Then we set y to equal 5. Then since `x == 5`, and `y == 5`, that means `x == y` is `True`, so we print "goodbye".

Then, because `x = 3` is indented such that it is part of the else block, we never run that code.

However, since `y = 4` is _not_ indented, it is run regardless of the outcome of the if-else block. You can think of things further to the right as "belonging to" things further to the left.

I would encourage you now to take some time to play with the `nesting.py` program in this lesson's Examples. Nest and un-nest statements, move things around, change values, add if-else blocks. See how nesting really ticks for yourself, it will become very important very quickly.

## Homework

#### Larger Number

Write a program called `largernumber.py` that will

1. prompt the user for a number
2. prompt the user for another number
3. print a statement indicating whether the first or second number was larger.

#### Expected Behavior

Enter a number: 40

Enter another number: 30

The first number was larger.

### Calculator

Write a program called `calc.py` that will

1. prompt the user for a number
2. prompt the user for an operator (+, -, /, \*)
3. prompt the user for another number
4. print the result of applying the operator to the two numbers

#### Expected Behavior

Enter a number: 5

Enter an operator (+, -, /, \*): \*

Enter another number: 3

15

### Absolute Value

Write a program called `absolutevalue.py` that will

1. prompt the user for a number
2. print the [absolute value](https://en.wikipedia.org/wiki/Absolute_value) of that number

#### Expected Behavior

Enter a number: -1

1

Enter a number: 1000

1000
