---
title: "Darwinian Java Cheat Sheet"
# title: "The Darwinian Approach to API-culture"
layout: post
date: 2021-12-12 20:05
tag:
- java
- dev-diary
headerImage: false
blog: true 
blog-highlights: false
description: "natural selection is case by case pragmatism at its finest"
category: blog
author: nicholaschin
externalLink: false
---

## Basics

1. Java Application
- Java applications tend to be ran as a single process. Within that process, applications can utilize independent "threads"of execution to perform tasks in parallel.
- A typical java web server has hundreds of threads. Each request to the server is handled on its own thread, and modern Java web servers are typically non blocking. 

Java advantages 

## OOPS

Advantages 
- Simplicity (models real world objects)
- Modularity 
- Modifiability (easy to make changes, changes inside a class won’t change others)
- Maintainability (separate classes easier to fix individually)
- Reusability

Procedural programming vs OOPS 
- Procedural 
    - Importance of sequence of function execution
    - Top down
- OOP
    - States and behaviours of objects 
    - enca[sulation 
    - Bottom-up paradigm 
    - Much more maintainable bc of classes (separate)
    - More code reuse

Abstraction
- Shows only the necessary + relevant features of an object, hide all others 
- Used to model structure of real world objects
- Only show switch of TV, not all the channels/functions of TV

Encapsulation 
- An OOP characteristic that allows you to encapsulate things that shouldn’t be modified by other parts of your code 
- Out of class encapsulation: wrapping up both fields + methods in same class and making them PRIVATE (other classes cannot access)
- Inner class encapsulation: function one and two both have I++ but it’s unique/availablle only to each function 
- <a href="https://beginnersbook.com/2013/04/oops-concepts/#1">Example</a>
- Public, private, protected

*Access modifiers: scope of which class/method/fields can be accessed by other class/methods/fields* 

Inheritance
- Levels of inheritance: single layer, multi layer, hierarchical 
- Child class can use some/all of the states/behaviors of its parents class 

Polymorphism: Method take more than one form 
- Static p: overloading
- Dynamic p: overriding 

Overloading
- Same method name; different implementation 
- Same method with different arguments, may or may not return same data type
- Arguments vary by: 
    - Sequence 
    - Data types
    - Number of parameters 
Overriding
- when we declare the same method name for child class and parent class (child and parent both contain same method)
- Child class can use `super.func` to make its method run exactly how parent class method runs 
- Same method names with same arguments, same return types too (between parent and child) 
- The main advantage of method overriding is that the class can give its own specific implementation to a inherited method without even modifying the parent class code.
- <a href="https://beginnersbook.com/2014/01/method-overriding-in-java-with-example/"> Example </a>

Abstract class vs Interface
- A:
    - Method implementation 
    - Extends 
    - M:1
    - For skeletal implementation 
    - CANNOT CREATE INSTANCES of objects 
- I: 
    - Implements 
    - No method implementation 
    - M:M
    - Specification 

## Data structures
1. String (immutaable)
2. Object (stored directly in heap)
3. List *interface* (maintain insertion order, include duplicate elements, can have null entry)
- ArrayList & LinkedList are all implementations of List interface (and part of the Collection framework in *java.util.package*)

Arrays ()
- Fast lookup if you know what position
- Costly insertion/deletion 
- Fixed size, resize each time to add new elements by creating new array and re adding those elements

ArrayList: dynamic array, index based, best for store and fetch, increases size by half
    - Same as Array
    - Except it is dynamically resizable (don’t need to determine size beforehand, but still need to declare capacity)
LinkedList: doubly linked list, best for adding and removing

ArrayList vs LinkedList
AL
- Fast lookup if you know what position
- Costly insertion/deletion
- Fixed size, resize each time to add new elements by creating new array and re adding those elements
LL
- Expensive lookup insert / delete if not at head/tail O(n) time
- More memory usage than arrays (pointer allocation)
- More memory efficient than arrays (dynamically resizable capacity)

4. Map
- key value pair, unique key
- HashMap : no order, can have single null key
- LinkedHashMap : insertion order, can have single null key
- TreeMap : sorted based on key, can’t have any null key

TBC


## Garbage Collection 

- Java runtime environment deletes objects when no longer being used. Memory is freed by objects not needed
- Unlike C++/C programmer is responsible for creation/destruction of ALL objects (failure to manage leads to OutOfMemory Errors)
- So in java programmer need not care about all those objects
    - Garbage collector best example of Dameon thread 
        - Low priority
        - Always running in background 
    - Main priority of GC is to free heap memory by destroying unreachable objects 
        - Object is unreachable iff it doesn’t contain any reference to it 

Memory allocation for global/local
- global: lifetime until the end of program 
- Local: until method ends 


## Exception handling 

- Throwable (**exception** and **error**)
- Exception (handled using *try-catch* block or *throws*)
- Error (cannot be handled, irrecoverable, i.e StackOverflowError)
- Checked exception (found at compile time - i.e ClassNotFoundException) -> app will not even boot
- Unchecked exception (occur during runtime - i.e NullPointerException) -> app will run until an exception occurs (but not caught)
- Finally (block after try/catch, optional)



SOAP vs REST vs RPC vs HTTP
TBC 
https://github.com/nicholaschinjie/tmdbMovieAPI 

