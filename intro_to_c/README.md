# Introduction to C Programming

C is a general-purpose programming language initially developed by Dennis Ritchie at Bell Laboratories. 

As C is a Compiled Language, a compiler is a program that converts high-level code (like C) into machine code that runs on the system. 
Before a program is executed, the compiler compiles the program and turns it into a binary executable, whereas in an interpreted language like Python, there is an interpreter that converts from human-readable into machine-readable code as you go through the program without the need for a separate compilation step.

Many operating systems, as well as Perl, PHP, Python, and Ruby, are written in C.
C is one of the common programming languages used in HPC.

Table of Contents:
* [Basics of C - Part One](#simple)

 * [Data Types](#dt)
	* [Basic Data Types](#bdt)
	* [`printf` function](#pf)
	* [Arrays](#arrays)
* [Loops](#loops)
	* [While Loop](#while)
	* [`do-while` Loop](#dowhile)
	* [`for` Loop](#for)
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

<ins>To specify Output File Name </ins>:
To compile the C program, use the gcc compiler to compile the C code into an executable:
```
$ gcc -o simple simple.c
```
-o is compiler flag that allows you to name the executable

To view the list of files in the directory:
```
$ ls
simple  simple.c
```
Run the program:
```
#./simple
The value of this integer is 3
```

### <a name="dt"></a>2. Data Types
Variables are named storage areas

For example, `int a = 5` creates a variable (storage area in memory) named “a” and saves the value of 5 in that memory location.

Variables of different data types occupy different amounts of memory and can store different ranges of values, and these variables must be declared before use.

### <a name="bdt"></a> Basic Data Types

| Name          | Type          | Range of Values | Size (B) |
| ------------- | ------------- | -------------   | -------------   |           
| Char          | Character     | ASCII Characters| 1  |
| Int		 | Integer   | -2,147,483,648 to 2,147,483,647   | 4 |
| Float  | Decimal (precision to 6 places)   | 1.2e-38 to 3.4e38   | 4 |
| Decimal  | Decimal (precision to 15 places)   | 2.3e-308 to 1.7e308   | 8 |

### <a name="pf"></a> Printf Function
#### Formatted Output with `printf` function
<ins>Example 1</ins>:

Code:
```
printf("Hello World");
```
Output:
```
 $ ./a.out
Hello World$
 ```
Result: Hello World

<ins>Example 2</ins>:

Code:
```
printf("Hello World\n");
```
Output:
```
 $ ./a.out
Hello World
$
 ```
Result: Hello World (with a new line)

### Format Tags: represented by a percent sign (%) followed by a character that specifies the type of formatting
* %c: Character
* %d: Integer
* %f: Floating-point number
* %s: String

 <ins>Example 3</ins>: 
```
int i = 2;
printf(“The value of the integer is %d\n”, i);
```
* i represents the variable whose value is used in the format tag

Result: The value of the integer is 2
 
 <ins>Example 4</ins>:
 ```
float x = 3.14159;
printf(“The value of the float is %.2f\n”, x);
```
* x represents the variable whose value is used in the format tag

Result: The value of the float is 3.14
 
### <a name="arrays"></a> Arrays
### C Arrays - Data structure that holds a fixed number of data elements of a specific type

```
int A[10]; // declares an array of 10 integers
```
| A[0]          | A[1]          | A[2] | A[3] | A[4]         | A[5]        | A[6] | A[7]|  A[8] | A[9]|
| ------------- | ------------- | -------------   | -------------   | ------------- | -------------   | -------------   | ------------- | -------------   | -------------  |       

* Each Element is 4 bytes for an integer

To assign values to the array elements,
```
A[0] = 7;
A[1] = 32;
A[2] = 256;
A[3] = 17;
A[4] = -20;
A[5] = 22;
A[6] = 1;
A[7] = 0;
A[8] = 59;
A[9] = -2;
```

```
printf(“The value of A[3] = %d\n”, A[3]);
```
Output:
The value of A[3] = 17

Example that shows the use of variables, arrays, and the printf() function, as well as how to find the size of data types using the sizeof() function:
```
/*------------------------------------------------------------
Program that prints that value of several variables to the
screen along with their size in bytes (in a table format).
------------------------------------------------------------*/

#include <stdio.h>

int main(){
	
    char a      = 'X';
    int i       = 22;
    float x     = 3.14159265358979323846264338327;
    double y    = 3.14159265358979323846264338327;
    char pi[31] = "3.14159265358979323846264338327";

    printf("\n--------------------------------------------------------------------------\n");
    printf("%-20s %-20s %-20s %-20s \n", "Variable", "Data Type", "Value", "Size (B)");
    printf("--------------------------------------------------------------------------\n");
    printf("%-20s %-20s %-20c %-20lu \n", "a", "char", a, sizeof(char));
    printf("%-20s %-20s %-20i %-20lu \n", "i", "int", i, sizeof(int));
    printf("%-20s %-20s %-20.16f %-20lu \n", "x", "float", x, sizeof(float));
    printf("%-20s %-20s %-20.16f %-20lu \n", "y", "double", y, sizeof(double));
    printf("--------------------------------------------------------------------------\n");
    printf("Actual value of pi ( 29 decimal places ): 3.14159265358979323846264338327\n\n");

    return 0;
}
```

Output:
```
--------------------------------------------------------------------------
Variable             Data Type            Value                Size (B)             
--------------------------------------------------------------------------
a                    char                 X                    1                    
i                    int                  22                   4                    
x                    float                3.1415927410125732   4                    
y                    double               3.1415926535897931   8                    
--------------------------------------------------------------------------
Actual value of pi ( 29 decimal places ): 3.14159265358979323846264338327
```


### <a name="loops"></a>3. Loops

### <a name="while"></a>a. While Loops

```
while(expression){
// Execute loop statements until expression evaluates to 0
}
```
* The expression is evaluated before each iteration

Example of while loop (03_loops/while_loop/while_loop.c):
```
#include <stdio.h>

int main(){

    float x = 1000.0;

    while(x > 1.0){
        printf("x = %f\n", x);
        x = x / 2.0;
    }

    return 0;
}
```

To compile and run the code:
```
$ gcc -o while_loop while_loop.c

$ ./while_loop
x = 1000.000000
x = 500.000000
x = 250.000000
x = 125.000000
x = 62.500000
x = 31.250000
x = 15.625000
x = 7.812500
x = 3.906250
x = 1.953125
```

### <a name="dowhile"></a> b. Do While Loops

```
do {
// Execute loop statements until expression evaluates to 0
} while (expression)
```
* The expression is evaluated after each iteration

Example of while loop (03_loops/while_loop/do_while_loop.c):
```
#include <stdio.h>

int main(){

    int j = 10; // Declare integer j and set its value to 10

    /* --------------------------------------
    do while loop
        -> Executes statements at least 1 time, 
           even if condition is not met 
    -------------------------------------- */
    do {
        printf("do-while: j = %d\n", j);
        j = j + 1;
    } while(j > 10 && j < 20);

    return 0;
}
```
To compile and run code:
```
$ gcc -o do_while_loop do_while_loop.c

$ ./do_while_loop
```
Output:
```
do-while: j = 10
do-while: j = 11
do-while: j = 12
do-while: j = 13
do-while: j = 14
do-while: j = 15
do-while: j = 16
do-while: j = 17
do-while: j = 18
do-while: j = 19
```
### <a name="for"></a>c. For Loops

```
for(initialization; conditional_expression; iteration){ 
// loop statements
}
```
* conditional_expression: Evaluated before body of loop
* iteration: Evaluated after body of loop

Example of for loop (03_loops/for_loop/for_loop.c):
```
/*------------------------------------------------------------
Program showing the basic idea of a for loop. For each
iteration of the loop, it prints the iteration number (i) 
along with the sum of all values of i up until that point.
------------------------------------------------------------*/

#include <stdio.h>

int main(){

    int N   = 10;
    int sum = 0;

    for(int i=0; i<N; i++){

        sum = sum + i;
        printf("Iteration: %d, sum = %d\n", i, sum);

    }

    return 0;
}
```

To compile and run code:
```
$ gcc -o for_loop for_loop.c

$ ./for_loop
Iteration: 0, sum = 0
Iteration: 1, sum = 1
Iteration: 2, sum = 3
Iteration: 3, sum = 6
Iteration: 4, sum = 10
Iteration: 5, sum = 15
Iteration: 6, sum = 21
Iteration: 7, sum = 28
Iteration: 8, sum = 36
Iteration: 9, sum = 45
```
<ins>Continue Statement</ins>:
When a continue statement is encountered within a loop, the remaining statements in the loop body (after the continue) are skipped and the next iteration of the loop begins.

Example of continue statement(03_loops/continue/continue.c):
```
/*------------------------------------------------------------
Program showing a continue statement within a for loop. The 
loop iteration number is printed except for the value 7 since
the continue statement moves on to the next iteration of the 
loop.
------------------------------------------------------------*/

#include <stdio.h>

int main(){

    for(int i=0; i<10; i++){

        if(i == 7){
            continue;
        }

        printf("Loop iteration: %d\n", i);
    }	

    return 0;
}
```
To compile and run code:
```
$ gcc –o continue continue.c
$ ./continue
Loop iteration: 0
Loop iteration: 1
Loop iteration: 2
Loop iteration: 3
Loop iteration: 4
Loop iteration: 5
Loop iteration: 6
Loop iteration: 8
Loop iteration: 9
```
<ins>Break Statement</ins>:
When a break statement is encountered within a loop, the loop is terminated.

Example of break statement(03_loops/break/break.c):
```
/*------------------------------------------------------------
Program showing a continue statement within a for loop. The 
loop iteration number is printed except for the value 7 since
the continue statement moves on to the next iteration of the 
loop.
------------------------------------------------------------*/

#include <stdio.h>

int main(){

    for(int i=0; i<10; i++){
        if(i == 7){
            continue;
        }
        printf("Loop iteration: %d\n", i);
    }	

    return 0;
}
```
To compile and run code:
```
$ gcc –o break break.c
$ ./break
Loop iteration: 0
Loop iteration: 1
Loop iteration: 2
Loop iteration: 3
Loop iteration: 4
Loop iteration: 5
Loop iteration: 6
```

### <a name="if"></a>4. If Statements
### <a name="functions"></a>5. Functions
### <a name="add"></a>6. Addresses and Pointers
### <a name="mem"></a>7. Memory Allocation
### <a name="exercises"></a>8. Exercises
