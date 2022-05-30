
# The Design of Dance Dance Revolution Studio
## Table of Contents
1. [The Purpose of this Document](#the-purpose-of-this-document)
2. [Programming Language Choice](#programming-language-choice)
3. [A Breakdown of Fundamental Tasks](#a-breakdown-of-fundamental-tasks)

## The Purpose of this Document
This document is meant to cover in depth the design choices - that is, the programming language choice, data structure design, function design, etc., that go into designing this program.  

That way, not only will others be able to understand what I am doing, but also I am trying to do with each component in this program.  

This document, I hope, will also be able to help keep my ADHD-ass on task with regards to developing this software in a logical manner that doesn't overwhelm me to no end.

## Programming Language Choice
For this program, I decided to go with C, with the Win32 API driving the GUI functionality.  

The choice of using C was due to a combination of speed, and control over the design of various data structures, since this suite will be doing a lot of processing of binary and text data, some of which can be rather large (depending on whether one loads a game executable, or disc image, and (if a disc image) the game being loaded.  

This includes the ability to do various tricks with raw pointers that I cannot do in other languages such as Java and C# that make this processing easier to implement effectively / quickly, and allows these tasks to be done (RELATIVELY) lightning fast.  

Also, fuck Java's lack of unsigned integer types. 

Also also fuck C#'s array size being limited to ~2GB files, making reading huge files w/o using a file stream impossible (which is by design).

[Back to Top](#table-of-contents)

## A Breakdown of Fundamental Tasks
This program will need to do the following at the very least to facilitate editing games in this program:

1. Be able to read game executables, AND full game disc images
2. Be able to identify the game (executable OR disc image) being loaded as a valid Dance Dance Revolution game
3. Be able to load specific configuration files identifying key data points in each game, and metadata about said data
4. Be able to use the metadata about that data to facilitate easy editing in various user-friendly editor windows
5. Be able to save edited file data, and game configuration information as a separate "project" for future editing that doesn't require reloading the executable or disc image to continue editing, but will allow for 

[Back to Top](#table-of-contents)
