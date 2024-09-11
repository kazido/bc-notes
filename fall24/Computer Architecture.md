---
id: Computer Architecture
aliases: []
tags: []
Class: CSCI 4200
Created: 2024-08-29T10:01
Type: Lecture
---
## **Code Pipeline**

source code

ex:
```python
print("Hello World!")
```
`print("Hello World!")`

→ pre-processor

scriptable text editor that removes the spaces from the source code

→ temp file

→ compiler

gives errors

compiler will compile the source code into an object file for a specific target.

the ==target== is the operating system/processor combo

the compiler’s output is in Assembly

→ assembler

takes the assembly code and translates it into machine instructions

→ object file (.obj)

machine instructions that the computer can run, but not a runnable program yet

→ linker

==executable (.exe)==

  

x86 - line of intel processors

8088 → 8086 → 80286 → 386 → 486 → ~~586~~ pentium → pentium 2 → pentium 3 → pentium 4 → celeron

  

register - a chunk of RAM directly on the CPU (functional part of the CPU)

limited by the bit size of the processor (register of a 64 bit processor is 64 bits)

essentially a variable in Assembly

general purpose registers (can be messed with by the user)

specific purpose registers (cannot be touched)

  

  

## The C Language

```JavaScript
// This code wouldn't work because function 'b' is not defined yet.
void a( )
{
	b();
}
void b()
{
}
// So let's try moving function 'b' above function 'a' so that it is defined.
```

  

```JavaScript
// That would work, until we want to call function 'a' in 'b'.
void b(char c)
{
	a(1, 2);
}
void a(int a, int b)
{
	b(x);
}
// To solve this problem, we use function prototypes.
```

### Function Prototypes

The signature of the function which contains just the data types. The purpose of this is to tell the compiler that the function exists so that it’s not ==undefined==.

The prototype for function ‘a’ looks like:

```JavaScript
void a(int, int);
```

  

### Header Files

Header files contain function prototypes and other declarations that can be shared across multiple source files. They are typically included at the beginning of a C program using the \#include directive. This allows the compiler to know about functions and variables defined in other files, preventing "undefined reference" errors during compilation.

Common header files in C include:

- stdio.h - for input/output operations
- stdlib.h - for memory allocation, random numbers, and other utility functions
- string.h - for string manipulation functions

```C
\#include <stdio.h>
//OR
\#include "C:/something/header.h"
```

> [!important]  
> The # sign is actually a command for the pre-processor. \#include copies the contents of the file and pastes it at the current line.  

**Other Preprocessor Commands**

```C
// If not defined
\#ifndef HEADERNAME_H
// Define
\#define HEADERNAME_H
\#define CONSTANT 101
\#define OTHER_CONSTANT 502
\#endif
```

> [!important]  
> Constants are simply the preprocessor searching for the constant name and replacing it with whatever follows.  

Careful not to include semicolons in \#define because it will take the semicolon and place it in your code where that constant is. Meaning if you have a constant in the middle of an equation, the semicolon will just end it.

  

`cd /` takes you to the root of the file system

- /boot - takes you to the linux kernel
- /dev - contains external drives like hard drives
- /etc - contains config files
- /var - contains log files
- /bin - holds binaries
- /sbin - holds system binaries
- bashrc file runs before each terminal boot up

  

**Big Endian** vs. **Little Endian**

- Endian is the direction in which bits are assigned priority.
- in Big Endian, we put the most significant digits on the left of the bit (like regular numbers)
- in Little Endian, it’s reverse. Most important digits on the right of the bit.
    - There is no difference in performance, it just depends on how the physical circuitry was built.

  

**Twos-Complement**

- The way that computers store negative numbers.
- The first bit is the sign AND the value.
    - `1000 0000` is `-128`
    - `1100 0000` is `-64`
    - `1111 1111` is `-1`

  

**Bit Shifting**

Suppose we have 4 small pieces of data to store.

a, b, c, and d

Each is one byte.

You could either:

- create 4 separate 1 byte variables
- create one integer

> [!important]  
> word: the smallest addressable unit of memory that can be accessed by the processor. In most modern systems, a word is typically 32 or 64 bits.

### Pointers in C
```c
int x = 5;
printf("Variable x is located at %p\n", &x)
```
The above code first **allocates** spaces for an integer *(usually 4 or 8 bytes)* with the name `x` and stores `x` in the **memory location** referenced by the name `x`. the association between 'x' and the location *does not* change! you can see the location by referencing the `&` (address-of) operator.

**Pointer**: A pointer is a variable that holds a memory address.
	Pointers are declared using the asterisk `*` operator
