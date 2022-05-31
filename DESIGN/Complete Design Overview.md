
# The Design of Dance Dance Revolution Studio
## Table of Contents
1. [The Purpose of this Document](#the-purpose-of-this-document)
2. [Programming Language Choice](#programming-language-choice)
3. [Identifying Essential Fundamental Tasks](#identifying-essential-fundamental-tasks)

## The Purpose of this Document
This document is meant to cover in depth the design choices - that is, the programming language choice, data structure design, function design, etc., that go into designing this program.  

That way, not only will others be able to understand what I am doing, but also I am trying to do with each component in this program.  

This document, I hope, will also be able to help keep my ADHD-ass on task with regards to developing this software in a logical manner that doesn't overwhelm me to no end.

## Programming Language Choice
For this program, I decided to go with C, with the Win32 API driving the GUI functionality.  

The choice of using C was due to a combination of speed, and control over the design of various data structures, since this suite will be doing a lot of processing of binary and text data, some of which can be rather large (depending on whether one loads a game executable, or disc image, and (if a disc image) the game being loaded.  

This includes the ability to do various tricks with raw pointers that I cannot do in other languages such as Java and C# that make this processing easier to implement effectively / quickly, and allows these tasks to be done (RELATIVELY) lightning fast.  

Also, fuck Java's lack of unsigned integer types. 

Also also fuck C#'s array size being limited to ~2GB files, making reading larger files w/o using a file stream impossible (which is by design).

[Back to Top](#table-of-contents)

## Identifying Essential Fundamental Tasks
Essential fundamental tasks are those tasks that are absolutely needed in order for this program to function, to allow for desired features to be implemented, and for the user to get out of using this program the intended experience/functionality.

These fundamental tasks include:
1. Being able to load game executables, as well as game disc images (ISO, BIN/CUE, etc.) into memory, some of which can be rather large (> 2GB)
2. Being able to identify the game loaded as being a valid Dance Dance Revolution title, or not.
3. Being able to load configuration files that tell the program what game is loaded, what data values are where, and information about them.
5. Making said configuration data modular enough where one can add, subtract, or modify with ease one or more component while having the original ("default value") remain in case a revert is desired.
6. Making it so that one doesn't need to retain the actual game in memory during the duration of editing data values, especially when a rather large game ISO image is loaded.
7. Making sure that if the user does not keep the game in memory, that the location of the file is preserved so the game can be loaded to, and written to when a save is desired.
8. Allowing for the configuration data, and all data - altered, and original backup - to be saved in a "project" file so the user can resume editing without having to reload the game image every time they open DDR Studio.
9. When writing a project file's game changes to a game, allow the user to find a copy of the executable or disc image if for whatever reason the saved file has been moved, or deleted (but also exists elsewhere). 

[Back to Top](#table-of-contents)

