---
Created: 2023-09-28T13:53
Class: CSCI 1140
Type: Lecture
Materials:
  - "[[Java.java]]"
---
Java.io

General Input Reader

Static type

Static Initializer Block

Loops

Types of Loops

Do While Loop

While Loop

For Loop

Arrays

Accessing data

Multidimensional Arrays

Copying Arrays

Making an array without knowledge of the size

Equality

Properties of Equality

Composition

Interface

Bubble Sort

Spring 2024

Hash Code

Linked Lists (cont.)

Generics

Stacks

Wildcard

Exam 1

Queues

Binary Search Trees

Hashing

Maps / Dictionary

## Java.io

> [!important]  
> IO stands for input / output  

Devices are either a _==source==_ or a _==sink==_

A ==_source_== is a device that data is being read from.

A ==_sink_== is a device that data is being written to.

|**DEVICES**|**FILTERS**|
|---|---|
|ByteArray / CharArray|Buffer|
|File|Data|
|RandomAccessFile|InputStreamReader/OutputStreamWriter|
||Object|
||Print|
||Pushback|
||SequenceInputStream|
||StreamTokenizer|

```Java
System.out.println("Hello world.");
System.err.println("Something went wrong...");
```

- ==**Java 1.0 - uses ASCII**==
    
    InputStream
    
    OutputStream
    
- ==**Java 1.1 - uses Unicode**==
    
    Reader
    
    Writer
    

> [!important]  
> most source code is written in ASCII  

---

```JavaScript
try {

// code that could throw an error

} catch(ExceptionType exceptionName) {

// handle the error

}
```

> [!important]  
> Don’t forget french braces on conditionals; it will only run the first line after if you do  

### General Input Reader

- `BufferedReader` gives speed
    - `InputStreamReader` allows us to read in ASCII from the keyboard using `System.in`

```Java
import java.io.*;

public class Java { 
	public static final void main(String[] args) {
		BufferedReader keyIn = new BufferedReader(new InputStreamReader(System.in));
		
		System.out.println("Please enter a file name to read from.");
		String fileName = keyIn.readLine();

	}
}
```

---

## Static type

The static type is a type that is bound to a class.

Instead of a static variable being an instance variable, it is a class variable. Only one can exist at a time.

```Java
private static BufferedReader reader;
```

```Java
public static String readLine(String prompt) {
// code
}
```

To access a `static` method, you call `ClassName.methodName()`.

### Static Initializer Block

```Java
static {
// intialize static things
}
```

- Automatically run for you. Used to initialize static variables.
- Can call any static methods.
- Can reference any static variables.
- Primary advantage is that it can have as many lines of code as necessary.
    - You can use `try_catch` in this block.

> [!important]  
> Method overloading is when you have more than method with the same name, but different argument lists.  

---

## Loops

### Types of Loops

==**Top Checking Loops**==

Might never run. Condition has to be met before the loop will run.

- `while`
- `for`
- `for each`

**Bottom Checking Loops**

Will always run at least once.

- `do`

  

### Do While Loop

```Java
do {
	// code block that will run (will run at least once)
} 
// condition that must be met for the code to run
while (condition == condition);
```

### While Loop

```Java
while (condition == condition) {
	// code that will run
}
```

### For Loop

- ==pre-loop:==
    - runs before the loop
    - setup the loop control
    - move to condition
- ==condition:==
    - must be met for loop to run
    - test loop control
    - move to the body
- ==body:==
    - runs if condition is met
    - do the work
    - move to the post-loop
- ==post-loop:==
    - runs after the loop has run
    - modify the loop control
    - move back to the condition

```Java
for (pre-loop; condition; post-loop) {
	// code to run during loop
}
```

Will execute condition → body → post-loop until the condition is false.

---

## Arrays

- Arrays are lists of variables of the same type
- Arrays are objects, meaning they have attributes and methods (such as length)
- When initialized, reserve space in RAM for the amount and type of data.
    - The space reserved _cannot_ be changed.

**Set**

- not ordered
- no duplicates
- all same data type

**List**

- ordered
- allows duplicate values
- all same data type

  

### Accessing data

Create an array with:

`type[] reference;`

`reference = new type[size];` - initialize an array with `size`

Read as “reference is an array of type”

To access data, index the reference variable:

`reference[index]` - access the data stored at index `index`

`reference[2]` - access the data stored at index `2`

`reference[2] = 4` - set the data stored at index `2` to the value `4`

How do you process an array? - with a for loop

### Multidimensional Arrays

To create a multidimensional array, just add another set of brackets

`type[][] reference = new type[sizeX][sizeY]`

### Copying Arrays

```Java
float [] temp = new float[original[0].length + 1];
for(int i = 0; i < original[0].length; i++) {
	temp[i] = original[1][i];
}
original[0]=temp;
```

Another way to copy arrays is to use

`System.arraycopy(source array, starting index, destination array, starting index, # of elements)`

### Making an array without knowledge of the size

Say we have 5 employees, but we don’t know how many months of data they have yet.

`float[][] sales = new float[5][]`

Will create an array of 5 arrays of null pointers.

They _can_ point to 5 arrays of floats, but currently _don’t._

  

## Equality

The `==` operator only works for primitive data types. It checks to see if the two objects are aliases / pointing at the same object.

For objects, you can use the `.equals` method, which can be overwritten for custom logic in a class. This will compare the objects information.

  

```Java
public boolean equals(Object o) {
	if(o==null) {
		return false;
	}
	if(this==0) {
		return false;
	}
	if(o instanceof ClassNameHere) {
		// compare relevant attributes here to determine if the objects are equal
	}
	return false;
}
```

### Properties of Equality

```JavaScript
// transitive property
if x == y
and y == z
then x == z

// symmetric
if x == y
then y == x

// reflexive
x == x
```

  

## Composition

Composition is when classes use other objects as variables.

For example:

```JavaScript
public class X {
	String note;
	Classroom room;

	public boolean equals(Object o) {
		if (o == null) {
			return false;
		}
		
		if (o == this) {
			return true;
		}

		if (o instanceof X) {
			X ox = (X)o;
			
			
```

## Interface

“an interface is a group of related methods with empty bodies” - Java docs

Adds structure to code

Can write a method that processes an interface

```Java
// Interface class Animal. Must have empty methods
public interface Animal {

	public void breathe();

	public void sleep();

}

// Dog HAS to have all the methods that Animal has
public class Dog implements Animal {

	public void breathe() {

		System.out.println("Heave");

	}

	public void sleep() {

		System.out.println("Mimimimi");

	}

}

// We know that process will work because any class 
// implementing the `Animal` interface will have sleep()
pubic void process(Animal a) {

	a.sleep();

}
```

## Bubble Sort

- Great for small amounts of data
- loops through the data and compares current iteration to next iteration.
    - If current is greater than next, create a temp of the current, set the current to the next, then set the next to the current, effectively moving it up one spot. This continues until the data is in it’s correct spot.

# Spring 2024

## Hash Code

A unique integer (local to object type) which is another way of comparing objects (.equals method). If two objects have the same data in them, the hash code should return the same unique numbers.

  

The advantage of hash codes are that comparing integers are much faster than comparing anything else.

  

**Every class has a hash code method.**

You can use the hash code method of the wrapper class for primitive data types.

  

When in doubt, call hash code.

  

  

## Linked Lists (cont.)

- root → not an actual node, but rather a node reference
- to remove the first element in a linked list

```Java
root = root.next;
```

- Lists like this are called “singly linked list”

Circularly Linked List

- root → node → node → node → root
    - “Last” node points to the root, making a circle.

```Java
// If root exists, add a new node after root
if (root != null) {
	newNode.next = root.next;
	root.next = newNode;
} else {
// If root doesn't exist, create a new node 
// and set next to itself (making it circular)
	root = newNode;
	newNode.next = newNode;
} 
```

Another Linked List

- root → node → node → node ← end
    
    - Now we have an end to track the end of the list
    - Makes it much faster, since we can now just add elements directly to the end of the list, rather than have to traverse it every time to add.
    
      
    

## Generics

```Java
Class 
```

  

## Stacks

When you input data, it goes on top.

**Limited Stack -** set amount of space. fills up and can’t add anymore to the top.

- Push - adding to the top
    - If you try to add when there is no space left → `StackOverflowException`
- Pop - removing from the top
    - If you try to remove when there is nothing left → `StackUnderflowException`
- Peek - look at the value on the top

**Unlimited Stack -** linked list version of a stack.

  

## Wildcard

`print(<? extends Animal> List)`

Whatever is in List extends `Animal`.

Different from just using a Generic `<E>` and then passing in `Animal` in Driver because that doesn’t allow subclassing.

  

**Upper Limit**

`print(<? extends Animal> List)`

We can use any class `Animal` or below.

**Lower Limit**

`print(<? super Animal> List)`

We can use any class `Animal` or above.

  

# Exam 1

- 1 page of notes, front and back
- Blackboard, file responses
- Can use the Java Docs
- No queues or deques
- Don’t have to turn in Driver files, no need to compile anything

  

## Queues

`FIFO` - first in, first out

enqueue - add

dequeue - poll

## Binary Search Trees

- Recursive in nature
- Can store a lot of data

Better for the tree to be balanced.

→ Minimum height and each node should try to have both children filled

When deleting, we pick the _==in order successor==_ or the ==_in order predecessor_==.

- ==In Order Successor==
    - The value in the tree that immediately proceeds the root value.
- ==In Order Predecessor==
    - The value in the tree that immediately precedes the root value.

**To Delete:**

- move right
- move left while left ≠ null

If we delete a node with only one child, we are ==_promoting_== the child.

  

**Types of Trees**

- Full
    - When every non-leaf node has 2 children
- Complete
    - Always add starting from the left and move to the right
- Heap
    - Parent is greater than or equal to children

  

**INDEXING**

Easy way to find children when the complete tree is stored in an array

$p$﻿ = parent index

$c $﻿ = child index

==Left Child:== $p * 2 + 1$﻿

==Right Child:== $p * 2 + 2$﻿ OR $LC + 1$﻿

==Parent:== $(c-1)/2$﻿

  

Heapify Up: take an element, look at its parent, if it’s smaller, then swap them

Heapify Down: take an element, look at its children, and swap it with the largest child

Removing from a Heap

You can only remove the root, because that is the only node that we have information about. We have no idea where the smallest node is, so we can only remove the root because we KNOW it is the largest.

How? - Take the last added Node and make it the root. Then, reheapifyDown.

  

### Hashing

Placing data into an array using a formula to calculate the index. Usually, the formula is:

data % arraySize (% = mod)

==**Collision**== - When two pieces of data, placed into the formula, return the same index.

- Collisions occur more often when the array is close to full.
- If you wanted to copy the array into a bigger one, you would have to rehash every value using the new mod value (due to the change in array size).

==**Load Factor**== - How much data should be put into the array before creating a new one.

- The usual load factor is ==**70%**==
- If hashing becomes too slow, lower your load factor
- If you run out of memory, increase the load factor

==**Linear Probing**== - Looking for the next open space after the collision to put the new data. Upon reaching the end of the array, move to the beginning of the array.

**Bucket** - When you store another data structure in the array to hold collisions.

  

### Maps / Dictionary

Store data using ==**key**== **-** ==**value**== pairs.

- The ==**key**== is the identifier.
- The ==**value**== is whatever data you are storing.