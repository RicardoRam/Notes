# Background Information

### Program := sequence of instructions to a computer
### Compiler := Program that turns C code into basic machine-level instructions (1’s & 0’s) that the processor can understand
### Input & Output (I/O) := Information sent or received from user or external device while program runs
 
ex. 1

    #include <studio.h> //adds code from another file to this file
    int main() { //main function is a wrapper for core of program. When a program runs, main’s code is executed
    printf(“Hello World”); //outputs text to screen. "Hello World" is a string literal
    return 0; //return 0; in main means finish executing program
    }
    // ; := end of instruction
### Memory := where computer stores information (grid with cells)

### Variable := A section of memory reserved by a program and used as a placeholder for a value.

### Variable declaration statement Ex. int canada_population;

- Specify name of value (tell program how to interpret the number (binary) stored in memory)

- Specify name (numbers, letters, and underscores. Can’t start with number and case sensitive)

- End statement with semicolon

      
### Assignment Statement := tell computer to set value on right of equal sign and store it in the variable on the left.
    ‘=’ symbol is assignment operator
### Expression := ways to perform calculations using arithmetic and boolean logic
           := evaluates right of assignment operator once
### Arithmetic Operations
      addition(+)
      subtraction(-) 
      multiplication(*), 
      division(/) := gives integer result which is then converted to original type.
      Ex. double q=9/4 first calculates integer result and then converts it to a double 2.000
      modulo(%) := gives remainder of integer division
      Note: no exponent operator
 
### Data Types
      int := stores integer values. Assigned decimals are converted to their floor value.
        1 address, 4 bytes
      double := stores real numbers (limited though)
        2 addresses, 8 bytes of memory (“double” that of int)
      char := stores text characters. 
        Note: Because of ASCII, numbers 0-255 represent text characters and can be converted by arithmetic operations.
        Note: C interprets \n as a single character
 
### Readability & Documentation
- Operators should have spaces beside them
- Statements should have their own line
- Use pothole_case
- Declare similar variables together
- Declare initial value and final result variable separately
- Limit lines to < 79
- Add comments /* multi line */  or   // for single line comment
 
### Libraries := contain many functions that can be used once imported

#include := tells compiler signatures of functions. ex. Using the function printf requires the library stdio.h. We will get a warning/error if we try to use printf w/o importing it's library.

#include <stdio.h>  //standard I/O library. 
 
### Output to STDOUT
    printf() := prints text to screen (in stio library), doesn’t return value
        Takes a different number of arguments depending on number of format specifiers in first argument. Warned if more specifiers than values or if we use wrong specifier
        
Ex. printf(“%lf centimeters is %lf inches. \n”, cm, inches);

### Input from STDIN

    scanf() := reads formatted input from stdin
        Ex. scanf(“%f”, &cm);  /* & before cm gives scanf the location (memory address) of cm so it can change the value. (scanf needs for numeric values) */
 
 ## Compiling C Program
 
 Gcc hello.c compiler that produces an executable file. Default file produced is a.out 
 
    Optional arguments
    
    -o := specify name of executable file where gcc saves output
    
    -Wall := print out additional warnings
    
./<filename> := To run executable file in shell

 
 
Useful Format Specifiers

%i, %d := tell program to expect an integer. (must be provided)

    Ex. printf(“Here is integer %d\n”, age)
    
%f := floating point value

%.3f := .3 specifies maximum number of characters to be read in current reading operation

%lf := long float

%c := char

%s := string

%p := pointer
 
