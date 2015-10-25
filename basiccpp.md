# C++

## Audience
    This tutorial is for people whose first programming language is C++, it sould cover the very basics of c++ without being too heavy or dense.

## Prerequisites
    - Some math, addition subtraction etc.
    - How to use computers.
    - Setup environment.

## Setup and installation
    
    - I would recommend [CodeBlocks](http://codeblocks.org/downloads/26) as it is small easy to use and comes with compiler bundled. Worry not, if we know not what those words mean.
    - If we don't have/wont cant install any software we can use any of the online compilers like [cpp shell](cpp.sh),[ideone](ideone.com), etc.

## First Program, Hello World

    - It just print hello world on the screen. You should see a window with "Hello World" written in it.
    - Yeah everyone learns how to do this what ever programming language they learn.
    - This confirms your environment is working.
    
```cpp    
#include <iostream>

int main()
{
  std::cout << "Hello World!";
}
```

## Data

There are different types of data one would want to use when doing stuff in real world
Like 
    - letters, punctuation, symbols, like **ABCDEFGH...**, **,.:\"?$₹**.
    
    - Words and sentences and paragraphs, like **Keep the dream alive: Hit the snooze button.**.
    
    - Whole numbers like. **We have 5 fingers**, **Voldemort had 0 noses**, **There were 9 rings for mortal men**.
    
    - Real numbers like what we pay for your shampoo, **₹99.99** only. We will get to know why 99 and 99.99 are different in c++ later on.
    
    - Answers to questions like, **Does a cat own we? yes?  no?**. One can only say *yes* or *no* here right? *maybe* doesnt count.
    
    - We do have more, but that's it for now.
    
## Lets play a game.

So I have seen people do this in other languages like python and perl. So lets do it.

Our program here will secretly hold a number between 0 and 100 and we will have to guess it. If the guess is more than the answer, it should tell that **the guess is bigger** or if the guess is less than the answer, it should tell that **the guess is smaller**. Give werself a prize if we guess correctly. And also track how many attempts was required to guess it.

We will have to learn lot more to write this game. So lets go step by step.

### Reading an input

Lets just do the part where we guess the number here. Just one attempt for now.

```cpp
#include <iostream>

int main()
{
  std::cout << "Guess? ";
  int num;      
  std::cin >> num;
  std::cout << "Your guess was " << num;
}
```

Let's go through what it's doing here, line by line

**#include <iostream>**

    - This is called including a header file. *iostream* is the header here. This contains the mechanism for reading the input and displaying stuff on the screen.

**int main()**

    - Well the name says it, its `main`, the programs starts from here. lets not bother with the `int` now.
    - `{ and }` these are used to mark boundary or technically `scope` of main here.
    
**std::cout << "Guess? ";**

    - `std::cout` : `std` is called a `namespace`. It's short for *standard*, for an anlogy we can consider a bag and there are lots of stuff(technically called an `object`) in the bag, we give a name to the bag `std`. We have `cout` in the bag `std` and use `::` to represent that. And what's `cout`? well its an object. that handles out put its short for *console out* (console is that black screen we see when we run the program).
    - `"Guess?"` : This is called a string, in C++ we always represent a string inside double quotes.
    - `<<` : This is like a spoon. We are feeding the string `"Guess?"` to the `cout` using `<<`, so it can eat the string and print it on the screen. 
    - `;` : Whats the deal with this? with this we tell that this is the end of the instruction. We have to do this every line(almost).
    
**int num**

    - `int` means an integer like the stuf we can count on our fingers, 1, 2, 99 etc. and if we want to use an integer use `int`. 
    - `num` is a variable and `num` its name. we can name it however we want as long as it satisfies certain [rules](), and there are quite a few of them. You name them because we can access them easily later on.
    - Writing `int num;` is called as declaring a variable. Why variable? because we can change its value.
    
**std::cin >> num;**

    - `cin` like `cout` is an object and is inside the `std` bag (`namespace`), and it is used to read input as we type on the console.
    - `>>` : This is also like a spoon. We are taking any number we type on the screen and putting it into the variable `num`;
    
**std::cout << "Your guess was " << num;**

    - This prints out the string and the number we typed in. well we didnt do much here but these are the very basics.

### Arithmetic operations

We will go through arithmetic operations like addition subtraction here, in c++ here.

#### Addition (+)

Here we enter a number say *1* it is stored in `num1`, next we enter another number say *6* it is stored in `num2`.

We declare another integer `sum`, but what's this; can we assign value to it when we declare it? yes, its called initialization. `num1 + num2` adds *1* and *6* and assigns *7* to `sum`.

We see *Sum: 7* when it prints it out finally.

`+` obviously means addition and is called an `operator` 

```cpp
#include <iostream>

int main()
{
    int num1, num2;
    
    std::cout << "Enter num1: ";
    std::cin >> num1;
    
    std::cout << "Enter num2: ";
    std::cin >> num2;
    int sum = num1 + num2;
    std::cout << "Sum: " << sum;
}
```

Change the same program for subtraction `-`, multiplication `*`, modulo or reminder `%`.

Try giving negative numbers like -1, -2.

#### Division (/)

So why have a separate section for division, isnt it similar to multiplication or addition? No There is some difference here and it can be dangerous.

Suppose we try this program with `num1=10` and `num2=2`, one can say what's the difference. it is just plain old normal division `10/2=5`.

Now try this `num1=5` and `num2=4`, whats the answer? 1? shouldn't it be 1.25? 

This is because its an integer, it cannot store numbers after the decimal point. 

```cpp
#include <iostream>

int main()
{
    int num1, num2;
    
    std::cout << "Enter num1: ";
    std::cin >> num1;
    
    std::cout << "Enter num2: ";
    std::cin >> num2;
    int qu = num1 / num2;
    std::cout << "Sum: " << sum;
}
```
    
To overcome this we use `float` data type as it can store numbers like 99.99, 3.142 etc.

Just change `int` to `float` for `num1`, `num2` and `qu`. Give inputs of 5/4 and you will get 1.25 as the answer now.

Also try giving inputs like `1.25/10` or `10.1/2`.

```cpp
#include <iostream>

int main()
{
    float num1, num2;
    
    std::cout << "Enter num1: ";
    std::cin >> num1;
    
    std::cout << "Enter num2: ";
    std::cin >> num2;
    float qu = num1 / num2;
    std::cout << "Sum: " << sum;
}
```
    
Try the program for Addition, Subtraction and Multiplication with `float` similarly. give inputs like `22.4+44.2` and `22.4*44.2`.

Get your math straight, you can get reminders if you use `float`.

Try division with input of `1/0`. What happens?

For now substitute `float` with `double`, also a basic data type and check your program 

