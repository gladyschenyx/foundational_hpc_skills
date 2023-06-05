# Introduction to C Programming

# Introduction to C Programming

C is a general-purpose programming language initially developed by Dennis Ritchie at Bell Laboratories. 

As C is a Compiled Language, a compiler is a program that converts high-level code (like C) into machine code that runs on the system. 
Before a program is executed, the compiler compiles the program and turns it into a binary executable, whereas in an interpreted language like Python, there is an interpreter that converts from human-readable into machine-readable code as you go through the program without the need for a separate compilation step.

Many operating systems, as well as Perl, PHP, Python, and Ruby, are written in C.
C is one of the common programming languages used in HPC.

Table of Contents:
* The Basics - Part One
	* [Simple example](#simple)

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


