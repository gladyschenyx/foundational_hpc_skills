# Introduction to C Programming

C is a general-purpose programming language initially developed by Dennis Ritchie at Bell Laboratories. 

As C is a Compiled Language, a compiler is a program that converts high-level code (like C) into machine code that runs on the system. 
Before a program is executed, the compiler compiles the program and turns it into a binary executable, whereas in an interpreted language like Python, there is an interpreter that converts from human-readable into machine-readable code as you go through the program without the need for a separate compilation step.

Many operating systems, as well as Perl, PHP, Python, and Ruby, are written in C.
C is one of the common programming languages used in HPC.

Table of Contents:
* The Basics - Part One
	* [Simple Example](#simple)

 * [Data Types](#dt)
	* Basic Data Types
	* `printf` function
	* Arrays
* [Loops](#loops)
* [If Statements](#if)
* [Functions](#functions)
* [Addresses and Pointers](#add)
* [Memory Allocation](#mem)
* [Exercises](#exercises)

### <a name="simple"></a>1. Simple Example
```
/*------------------------------------------------------------
Program that prints the value of an integer to the screen.
------------------------------------------------------------*/
#include <stdio.h>

int main(){
    int a = 3;
    printf("The value of this integer is %d\n", a);
    return 0;
}

```

The `#include <stdio.h>` statement is a C preprocessor directive telling the compiler to include contents of the header file in angle brackets.

The `int main()` is a declaration of a function called main, which is where the execution of the program begins.  `main` is included in all C programs. The “int” indicates that the function will return an integer value.

`{` and `}` are curly braces that indicate the beginning and end of the main function.

`int a = 3` defines an integer called “a” and assigns it a value of 3.

`;` is a semicolon used to indicate the end of each statement.

`printf` is a function that sends formatted output to stdout (typically the terminal from which the program was run). Stdout refers to standard output, and when the user runs the program, it prints the output data to the display screen. `printf` is defined in the stdio.h header file, which includes the standard input/output functions. 

`return 0` is a return value “returned” to the run-time environment. Typically, a value of 0 indicates a normal/successful exit.

To compile the C program, use the gcc compiler to compile the C code into an executable:
```
$ gcc simple.c
```

An executable is named a.out by default. To view the list of files in a current directory, use the `ls` command: 
```
$ ls
a.out  simple.c
```

To run the program, use the following:
```
#./a.out
The value of this integer is 3
```
Specifying `./` before the command or program name indicates that the program should be found and executed in the current directory.


### <a name="dt"></a>2. Data Types
Variables are named storage areas

For example, `int a = 5` creates a variable (storage area in memory) named “a” and saves the value of 5 in that memory location.

Variables of different data types occupy different amounts of memory and can store different ranges of values, and these variables must be declared before use.

Basic C Data Types: 
| Name          | Type          | Range of Values | Size (B) |
| ------------- | ------------- | -------------   | -------------   |           
| Char          | Character     | ASCII Characters| 1  |
| Int		 | Integer   | -2,147,483,648 to 2,147,483,647   | 4 |
| Float  | Decimal (precision to 6 places)   | 1.2e-38 to 3.4e38   | 4 |
| Decimal  | Decimal (precision to 15 places)   | 2.3e-308 to 1.7e308   | 8 |

#### Formatted Output with `printf` function

### <a name="loops"></a>3. Loops
### <a name="if"></a>4. If Statements
### <a name="functions"></a>5. Functions
### <a name="add"></a>6. Addresses and Pointers
### <a name="mem"></a>7. Memory Allocation
### <a name="exercises"></a>8. Exercises
