# Unit 2: Variables and Operators

## Introduction
In its simplest form, a program performs **operations** on **data** and then outputs it. \
This unit, you will learn the different types of data and operators that can be used on them.

Because of how many basic concepts there are, Unit 2 is quite long.

> **Reminder:** Use `Ctrl`+`Shift`+`V` to open *Preview*. \
> You can drag around tabs or use `Ctrl`+`Shift`+`RightArrow` to split the *Editor*.

### Table of Contents
- [Introduction](#introduction)
    - [Table of Contents](#table-of-contents)
- [Comments](#comments)
- [Data Types](#data-types)
- [Variables](#variables)
    - [Declaring Variables](#declaring-variables)
        - [Naming Variables](#naming-variables)
        - [> Exercise: Your Information](#-exercise-your-information)
    - [Assigning to Variables](#assigning-to-variables)
        - [> Exercise: Bakery](#-exercise-bakery)
- [Operators](#operators)
    - [Arithmetic Operators](#arithmetic-operators)
        - [Updating Variables](#updating-variables)
    - [Comparison Operators](#comparison-operators)
        - [String Comparison](#string-comparison)
    - [Logical Operators](#logical-operators)
    - [String Concatenation](#string-concatenation)
    - [Order of Operations](#order-of-operations)
    - [> Exercise: Marine Life](#-exercise-marine-life)
- [Recap](#recap)
    - [Keyboard Shortcuts](#keyboard-shortcuts)

[Feedback](#feedback) \
[License](#license)

## Comments
<sub>(Detour: this concept is miscellaneous and is not related to the main subject)</sub>

Before we learn those concepts, you need to know about **comments**, which are messages embedded in the code that are ignored during program execution. \
These are useful for telling other programmers (including your future self) about your code. You will see them a lot in our provided code files. \
It can also be used to disable code without completely removing it.

A single-line comment is started with `//`, and everything after it until the end of the line is part of the comment.
```java
System.out.println("Hi!"); // Be nice, please!
// The below code won't execute, it's "commented out"
// System.out.println("Go away");
```
A multi-line comment spans multiple lines. Start one with `/*` and end it with `*/`; the text in between is part of the comment. \
They are typically styled as shown below:
```java
/*
 * Yes?
 * Maybe!
 * No.
 */
```

> **Tip:** Use `Ctrl`+`/` on selected lines to comment those lines out, or to uncomment commented lines.

## Data Types
When you're writing computer programs, you'll need to handle many different kinds of data. \
Java defines many distinct data types, essentially labels that you put on your data that tell the computer what kind of value something is. \
Let's look at a few common data types and their definitions!

- An **`int`** stores an integer, or a whole number. (E.g. `2`, `-10`, `578`)
- A **`double`** stores a decimal number. (E.g. `1.5`, `-4.0`, `48.002`)
- A **`boolean`** stores a value that is either `true` or `false`
- A **`String`** stores a sequence of characters. (E.g. `"Hello World!"`, `"as{t3r0g#mk&4k!!"`). You used these last unit

> **Warning:** Java code is case-sensitive. When using these data types later, remember that `String` is uppercase while the other types are lowercase.

Try it yourself!

What is the data type of each of the following values:
1. `30.4`
2. `":D"`
3. `15`
4. `false`
5. `"5"`

<details><summary>Answers</summary>

1. `double`
2. `String`
3. `int`
4. `boolean`
5. `String`
</details>

## Variables
What if you have a specific value you want to keep track of throughout the program? For example, the number of books at the library throughout the day or, whether a light switch is on or off.

In programming, we use **variables** to store and use data! \
Variables are like 'boxes' that programmers can put data in. After creating them, we can later check what value is in the box (multiple times possibly).

### Declaring Variables
In a program, you can **declare** and **initialize** a variable using this statement:
```
<datatype> <variable_name> = <value>;
```
For example, if I wanted to declare an `int` variable named `days` initialized with the value `2`, I would write:
```java
int days = 2;
```
Examples for different data types:
```java
int penguins = 0;
double length = 0.5;
boolean confirmed = true;
String greeting = "hi";
```

#### Naming Variables
> **Note:** In programming, "identifier" and "symbol" are synonyms for "name".

<u>Rules:</u>
- No white space (spaces, tabs, newlines)
- Only letters, digits, underscore `_`, and dollar sign `$` are allowed
- Name cannot start with a digit
- Cannot be a keyword or reserved word (special words used by Java). E.g. `int`, `boolean`, `class`, `var`
- Names are case-sensitive

<u>Conventions (best practice):</u>
- Spell the first word in all lowercase letters; capitalize the first letter of every subsequent word. E.g. "first name" would be `firstName`. This style is called *camelCase*
- Names should be descriptive, but not too long

> **Tip:** In VS Code, there are many shortcuts to rename things.
> - Use `F2` to rename a symbol
> - Use `Ctrl`+`F` to find and replace text; `Ctrl`+`Shift`+`F` to search project instead of file.
> - Use `Ctrl`+`D` or `Ctrl`+`Shift`+`L` to select multiple occurrences of text

#### > Exercise: Your Information
Inside [`PersonalInformation.java`](PersonalInformation.java), declare variables, with appropriate data types, for each of the following:
1. An `int` variable called `pets` set to how many pets you have
2. A variable called `gpa` set to a GPA
3. A variable set to your name
4. A variable called `isAlive` set to whether or not you're currently living

Then, use `System.out.println(<variable>);` to print out each of the declared variables.

<details><summary>Solution code</summary>

The values of your variables will differ from this example.
```java
public class PersonalInformation {
    public static void main(String[] args) {
        // Ignore everything above this line
        int pets = 1;
        double gpa = 4.0;
        String name = "SpongeBob";
        boolean isAlive = true;

        System.out.println(pets);
        System.out.println(gpa);
        System.out.println(name);
        System.out.println(isAlive);
        // Ignore everything below this line
    }
}
```
Output:
```
1
4.0
SpongeBob
true
```
</details>

### Assigning to Variables
To change the value of a previously declared variable, you can simply reassign it. An assignment statement looks similar to a declaration statement, but in assignment you don't put the data type because Java already knows what type it is from the declaration.
```
<variable_name> = <value>;
```
For example:
Say you're keeping track of how many types of vegetables are growing in your garden. Initially, there are 5 different kinds of vegetables, so:
```java
int vegetableTypes = 5;
```

But one day, a horde of bunnies uproots all of your carrots and lettuce! Now `vegetableTypes` has to be updated.
```java
vegetableTypes = 3;
```
Note that the value that was originally in the variable is gone, replaced.

Variables can also take on the values of other variables!
For example:
```java
int cats = 5;
int dogs = 10;
cats = dogs; // cats now has a value of 10
```
It's important to note that `cats` and `dogs` were not "merged" or "linked" - cats accessed the *value* of dog (`10`) and assumed that *value*. The `dogs` variable was not changed. \
If you then set `cats` to `1`, then `dogs` would still be `10`.

When declaring variables, you actually don't have to initialize them right away:
```java
boolean winner;
```
Then, you can assign it a value later. The variable can't be used until it is guaranteed to have a value. \
This is occasionally useful.

#### > Exercise: Bakery
[`Bakery.java`](Bakery.java) \
You have been tasked with keeping track of the desserts at the local bakery. 

1. At the start of the day, there are 40 pies and 70 cupcakes. Declare variables to keep track of them.
2. Someone comes in and purchases 25 pies (don't ask why), leaving 15 left. Update the `pies` variable so it stays accurate to the pies remaining.
3. A witch enters and incinerates all of your cupcakes. Update the `cupcakes` variable accordingly.
4. A different witch turns all of your remaining pies into cupcakes. Update both variables accordingly. When assigning to cupcakes, use your pies variable (instead of a "hard-coded" value of `15`).
5. Print out the number of pies on one line, and then the number of cupcakes on the next.
___
Check that your program gives the correct output:
```
0
15
```
If your program outputted `0` pies and `0` cupcakes left, check step 4 closesly.

<details><summary>Solution</summary>

```java
public class Bakery {
    public static void main(String[] args) {
        // 1. Declare your variables below; 40 pies and 70 cupcakes
        int pies = 40;
        int cupcakes = 70;
        // 2. Someone purchased 25 pies, leaving 15 left
        pies = 15;
        // 3. A witch incinerates your cupcakes
        cupcakes = 0;
        // 4. A witch turns your remaining pies into cupcakes
        cupcakes = pies;
        pies = 0;
        // 5. Print the number of pies and the number of cupcakes left
        System.out.println(pies);
        System.out.println(cupcakes);
    }
}
```
On step 4, `cupcakes` must be assigned to `pies` **before** `pies` is set to `0`. \
If the order of the two lines are switched, `pies` will already be `0` when `cupcakes` takes its value.

</details>

## Operators
We use symbols called **operators** to (you guessed it!) perform a variety of operations on values, called **operands**. \
There are many different types of operators, and we'll cover the most commonly used ones here!

An **expression** is a combination of operators and operands , which produces a single value when **evaluated**.

Parentheses `()` can be used to group operations when needed, similar to in math.

The equal sign `=` is technically an operator (assignment) and so may be used inside of expressions, but in general you should only use them as independent statements.

### Arithmetic Operators
These operators are used for mathematical calculations. Used on two numeric operands (`int` or `double`).

| Operator | Result | Example |
| - | - | - |
| `+` | Sum (addition) | `x + y` |
| `-` | Difference (subtraction) | `x - y` |
| `*` | Product (multiplication) | `x * y` |
| `/` | Quotient (division) | `x / y` |

If at least one of the operands is a `double`, the result is also a `double`. \
When both are `int`, the result is an `int`. <u>For division between two `int`s, the decimal part is removed from the result</u>: integer division **truncates** the result. \
So `3 / 2` gives `1`, and `3.0 / 2` gives `1.5`.

Examples!
```java
int x = 4;
int y = 2;

int z = x - y; // z is assigned 2 (4 - 2)
y = x / 2; // y is assigned 2 (4 / 2)
x = y / z; // x is assigned 1 (2 / 2)
```
> **Note:** Many other math operations such as absolute values, square root, and exponentiation, don't have built-in Java operators, \
> and are instead part of the built-in `Math` utility: `Math.abs(-1)`, `Math.sqrt(4.0)`, `Math.pow(2, 5)`.

#### Updating Variables
In many cases when assigning a variable, the new value expression also includes the variable itself. \
For example, increasing `x` by 1, or doubling `z`.

You can reference the variable as normal in the assignment, as it is still available before the assignment occurs.
```java
int x = 3;
int y = 3;
x = x + 1; // Increasing by 1
y = (y + x) * 2; // y = (3 + 4) * 2
```

This is so common that there are shorthands for certain cases:
```java
x = x + 1;
// can be written as
x += 1;
```
Formally, when the variable is the left operand of the final operation, you can shorten it with a **compound assignment**. \
This works with all arithmetic operators and a few others.
```
y /= 3.5;
z -= y;
```

The most common case of all is increasing by `1` (**increment**) or decreasing by `1` (**decrement**). \
So Java has shorthands for the previous shorthands:
```java
x += 1;
// can be written as
x++;

y--; // Subtract 1
```

### Comparison Operators
Comparison operators are used to compare two variables or values. These operators result in a `boolean`, either `true` or `false`. \
Also called relational operators.

| Operator | Result (`boolean`): Whether or not... | Example |
| - | - | - |
| `==` | the values are *equal to* each other | `x == y` |
| `!=` | the values are *not equal to* each other | `x != y` |
| `>`  | the first value is *greater than* the second value | `x > y` |
| `<`  | the first value is *less than* the second value | `x < y` |
| `>=` | the first value is *greater than or equal to* the second value | `x >= y` |
| `<=` | the first value is *less than or equal to* the second value | `x <= y` |

Examples!
```java
int x = 4;
int y = 2;
int z = 1;

System.out.println(x != y); // prints true because 4 doesn't equal 2
System.out.println(z > x); // prints false because 1 is less than 4
y = x;
System.out.println(x == y); // prints true because 4 is equal to 4
System.out.println(y <= x); // prints true because 4 is less than or equal to 4
```

#### String Comparison
String equality shouldn't be done with `==`. Instead, use `string1.equals(string2)`.
```java
String secretCode = "12345";
String input = "12345";
System.out.println(input.equals(secretCode)); // true
```
You can also use `string1.equalsIgnoreCase(string2)` to ignore case when checking.

### Logical Operators
Logical operators are used to operate on booleans and calculate logic. \
The operands are usually *boolean expressions* involving comparison operators.

| Operator | Result | Example |
| - | - | - |
| `&&` | Whether *both* operands are `true` | `x > 3 && x < 10` |
| `\|\|` | Whether *either* operand is `true` | `x < 20 \|\| x > 40 ` |
| `!` | Takes one operand. *Inverts* the boolean | `!(x > 0 && y > 0)` |

Examples!
```java
int x = 10;
int y = 5;
int z = 2;

System.out.println(y == 2 || x > 5); // prints true; even though the first conditional is false, the second is true and the `or` operator only needs one conditional to be true to returgive true
System.out.println(z < 5 && x < 5); // prints false; the `and` operator requires both conditionals to be true to return true, and the second conditional is false.
System.out.println(!(x <= y || z != 3)); // prints false; the `or` operator returns true (the second conditional is true), and the `not`operator reverses that result so it becomes false.
```

> **Note:** Be extra cautious with the `!` operator on complex boolean expressions. \
> The equivalent of `!(A && B)` is `!A || !B`. It is NOT `!A && !B`.

### String Concatenation
You can add together strings to form another string, made of the two strings squished together. This is called concatenation.

You can actually add strings to any value. When one of the operands is a `String`, the other value is implicitly converted into a string and then they are concatenated.

```java
System.out.println("Hello " + "World"); // Hello World
System.out.println("Count: " + 3); // Count: 3
```

### Order of Operations
Certain operators are evaluated first in an expression. Operators with higher **precedence** are evaluated first.

Within arithmetic, PE\[MD\]\[AS\] applies to the order of operations. \
String concatenation is considered the same as addition. When using it, check the order of evaluation closely.

Arithmetic operators have high precedence. They are followed by comparison operators, and logical operators. \
Assignment operators have lowest precedence. \
When there are multiple operators with the same precedence, the order is left to right for most operators.

Parentheses can force some operations to be evaluated first.

Example: the below two expressions are equivalent.
```java
1 + 2 * 3 > 4 && 5 < 6 * 7
((1 + (2 * 3)) > 4) && (5 < (6 * 7))
```

### > Exercise: Marine Life
[`MarineLife.java`](MarineLife.java) \
You're compiling a report of species of marine life in a small area of the Pacific Ocean.
1. You've documented **11 dolphins**, **8 octopuses**, **4 sea otters**, and **2 manta rays**. Declare variables to store how many of each animal you have documented, and when changes occur use operators to update them.
2. Recently, **2 new dolphins** were born. But also, a **single manta ray has died**.
3. The witch from the bakery **vaporizes 4 octopuses**.
4. Your boss wants to know if there are **more dolphins than octopuses**. Print the answer, true or false.
5. Your boss also wants to know if the **number of manta rays is equal to the number of sea otters**. Print the boolean answer.
6. On a single line, print out **`Number of animals: `** followed by the **total number of animals** (that you have documented and are current alive in the area).
7. If there are **less than 4 of an animal** in this area, your organization considers them endangered. Print a single boolean for whether __sea otters *and* manta rays are both considered endangered__.
___
Correct output:
```
true
false
Number of animals: 22
false
```
If your program shows the number of animals as impossibly high, check your order of operations in step 6.
<details><summary>Solution</summary>

```java
public class MarineLife {
    public static void main(String[] args) {
        // 1.
        int dolphins = 11;
        int octopuses = 8;
        int seaOtters = 4;
        int mantaRays = 2;
        // 2.
        dolphins += 2;
        mantaRays--;
        // 3.
        octopuses -= 4;
        // 4.
        System.out.println(dolphins > octopuses);
        // 5.
        System.out.println(mantaRays == seaOtters);
        // 6.
        System.out.println("Number of animals: " + (dolphins + octopuses + seaOtters + mantaRays));
        // 7.
        System.out.println(seaOtters < 4 && mantaRays < 4);
    }
}
```
For step 6, one can also declare a new variable for the number of animals.
</details>

## Recap
- Comments are created with `//` or `/*`+`*/`
- The common data types are `int`, `double`, `boolean`, `String`
- Declare and initialize variables with, e.g.: `int x = 1;`
- Variable names should be made of letters and digits, and styled in `camelCase`
- Assign new values to previously declared variables with, e.g.: `x = 2;`
- Arithmetic operators (`+` `-` `*` `/`) do calculations with numbers
- Update variables with compound assignment operators (`+=` `-=` etc.) and increment/decrement operators (`++` `--`)
- Comparison operators (`==` `!=` `>` `<` `>=` `<=`) compare numbers and give a boolean
- Logical operators (`&&` `||` `!`) perform logic on booleans, result in another boolean
- String concatenation (`+`) combines strings and other values into a string
- Operator precedence order, highest first, is: parentheses `()`, arithmetic (PEMDAS), comparison, logical, assignment

### Keyboard Shortcuts
| Keybinding | Command |
| - | - |
| `Ctrl`+`/` | Toggle line comments |
| `F2` | Rename symbol
| `Ctrl`+`F` | Find text in file |
| `Ctrl`+`Shift`+`F` | Find text in project |
| `Ctrl`+`D` | Select next occurrence |
| `Ctrl`+`Shift`+`L` | Select all occurrences |

## Feedback
Please provide feedback if you have any.
<details><summary>Possible feedback points</summary>

- Confusing explanations
- Knowledge, skills, or procedures that were required but weren't taught
- Too fast or too slow explanations; pacing
- Too hard or too easy exercises
- Step-by-step instructions that are not comprehensive/thorough enough, or didn't work
- Seemingly unnecessary or ineffective information or exercises
- Any improvements (e.g. wording) or more effective ways/formats to teach
</details>

___



## License
© 2025 @aatle, @spacepotatoes3

This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).
