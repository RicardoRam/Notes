# Background Information

### Program := sequence of instructions to a computer
### Compiler := Program that turns C code into basic machine-level instructions (1’s & 0’s) that the processor can understand
### Input & Output (I/O) := Information sent or received from user or external device while program runs
 
ex. 1

    #include <studio.h> //adds code from another file to this file
    int main() { //main function is a wrapper for core of program. When a program runs, main’s code is executed
    printf(“Hello World”); //outputs text to screen. "Hello World" is a string literal
    return 0; //return 0 in main means finish executing program
    ; := end of instruction
    }

### Memory := where computer stores information (grid with cells)

### Variable := program reserves a section of memory called a variable (placeholder for value)

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

#include := tells compiler signatures of functions. Will get a warning/error if we try to use printf w/o importing it's library

#include <stdio.h>  //standard input/output library. 
 
### Input, Output, Compiling 
- Can use functions w/o knowing how they work
    OUTPUT
    printf() := prints text to screen (in stio library), doesn’t return value
        Takes a different number of arguments depending on number of format 
specifiers in first argument. Warned if more specifiers than values or if we use 
wrong specifier
Ex. printf(“%lf centimeters is %lf inches. \n”, cm, inches);
    INPUT
    scanf() := reads formatted input from stdin
        Ex. scanf(“%f”, &cm);  /*& before cm gives scanf the location (memory 
address) of cm so it can change the value. (scanf needs for numeric values) */
 
Format Specifiers
%i, %d := tell program to expect an integer. (must be provided)
    Ex. printf(“Here is integer %d\n”, age)
%f := floating point value
%.3f := .3 specifies maximum number of characters to be read in current reading 
operation
%lf := long float
%c := char
%s := string
%p := pointer
 
Command line
cd := change directory
ls := list current working directory
    Optional arguments
    -F := see executable files (will have * after them), x means anyone can execute
    -l := check permissions
Gcc hello.c compiler that produces an executable file. Default file produced is a.out 
    Optional arguments
    -o := specify name of executable file where gcc saves output
    -Wall := print out additional warnings
./<filename> := To run executable file in shell
 
 
 
 
If/Else statements := if condition(only checked once) is true, execute statement in if block, 
else, execute statements in else block(if there is one) 
Variations
Can have multiple if statements and each will be evaluated every time.
Can have if and else if statements without an else block
 
Comparison/Relational Operators
Description
Operator
Less than
<
Greater than
>
Equal to
==
Greater than or equal to
>=
Less than or equal to
<=
Not equal to
!=
 
Conditional/Logical Operators
Operator Description
Operator
AND operator := True when BOTH expressions are true
&&
OR operator := True when one or both conditions are true
||
Not operator := negate
!
 
ex.
int x = (4 < 5);
printf(“x:%d”,x);
 
Prints x:1 since 
0 -> interpreted as false
1 -> interpreted as true
 
Neat trick: if(x) can be used to avoid dividing by 0. Ex. if(x) { y = 5/x }
 
Functions
Function Prototype := Tells compiler how to run program. Without one, we get a warning/error. Can declare and define function at the same time (if done above main).
name
return type
list of arguments (can be expressions or function calls (will be evaluated first))
Semicolon
    Ex. double fmax(double x, double y); //double fmax(double, double); also valid
If we call want to call a function from a different program, must tell compiler where it comes from using #include 
    Ex. #include <stdio.h>
 
Types
 
Data being stored
 
Currency
Long Integer
Also use lround from math library to round final answer.
Percents
Double (specify between 0 and 1)
 
 
 
Iteration
        
Loop := used when you want to repeat a set of instructions
 
For loop 
for(Initialization; Continuing Condition; Update) {
    Loop body
}
Initialize := set variable
Update := perform update after every iteration
Continuing Condition:=determine how long code runs (To find continuing condition, it’s useful to take condition we want loop to stop at and negate it)
 
While loop (use when loop structure doesn’t match for loop structure)
Just has condition (can add Initialization/Update ourselves)
while(i<5) {
    printf(“%d\n”,i);
}
 
Do while loop := executes loop body once before checking condition
Note: useful for user input
do {
    Loop body
} while (Continuing condition);
 
Break:= exits current loop. If break is used, typically add a flag (ex. An infinite loop like while(1)) to tell others something interesting is happening within loop. 
 
Continue := causes rest of one loop body to be skipped to next iteration. (Continue, if executed)
 
Pointers  := store memory addresses as values. Requires type of value you want to store to initialize.
Pointer Declaration := int *pt; 
Type is int * (read as “int star” or “pointer to int”). Space is irrelevant ( int *pt == int* pt == int * pt). In declaration, star is part of type, not dereference. (type = int*)
Dereference operator (*) := applied to a pointer and evaluates to the memory(value) at the address pointed to by pointer (ex. *pt = 9; is valid but int *pt = 9; means something else (declaration of new variable pt))
Dereference precedence is higher than DMAS(latter part of BEDMAS) but lower than ++, --, p[~].
 
-> := used to dereference a pointer to a struct only. ex. strcpy(friend->name, new_name);
 
char letter = ‘A’;
letter++; //now letter has the value ‘B’ because of ASCII table
 
&:= return address of variable
 
Pointers as Parameters
 
void apply_grade(char *grade_ptr) {
    //use *grade_ptr = within function to modify value stored in memory address pointer points to.
    (*grade_ptr)++; //to increment, first dereference operator, then increment operator
}
Call above function with the following.
char grade = ‘A’;
apply_grade(&grade); //function requires char * value, i.e an address
 
Array
Passing an array as a parameter only passes pointer to 1st address
If you need size of array, pass in size of array as well 
 
ex. int *A
sizeof(A) gives size of pointer to int
 
ex2. TRICKY QUESTION
void initialize(int *init_ptr) {
    *init_ptr = 7;
}

int main() {
    int *ptr = malloc(sizeof(int));
    initialize(ptr);
    return 0;
}
The main function dynamically allocates memory for ptr and then assigns its address to int *ptr. Since we want to modify ptr, we can pass in its address (*ptr) as an argument to initialize. Since the copy will have the same memory address value, initialize will modify the correct ptr.
 
ex3 HARD Q
void initialize(int *init_ptr) {
    init_ptr = malloc(sizeof(int));
    *init_ptr = 7;
}

int main() {
    int *ptr;
    initialize(ptr);
    return 0;
}
a copy of ptr (of type int *) is passed as an argument to initialize where the local copy is dynamically allocated memory and then assigned the value 7. This local copy lives within the scope of the initialize function and once it returns, there will be a memory leak.
 
The key difference between ex1 and ex2 is when the dynamic memory is being created.
 
Pointer arithmetic
 
x/y
default:= integer division for type int
different type depending on type. (ex.
floating point division if either is type f)
p += 1
p = p + (sizeof(type)*n)
 
 
 
 
 
Hexadecimal := 
0x0...4c
0x0...5c <- difference of 16 bytes
 
char i = ‘M’; //visualizer shows 4 bytes at a time. char takes up 1 byte, placed in last byte.
 
 
 
M
cc                cd            ce            cf
 
char *p = &i; <- stores address of ...cf
 
int *x = A;
 
How to increment pointers.
*(x+1) == x+ (sizeof(type)*1) == x[1]
 
incrementing the address pointed to by p increments all further calls to p.
 
 
Visualize Function Execution
 
 
Stack := section of memory used for static memory allocation(automatic storage duration). Allocation dealt with at compile time. A function call adds the function to the top of the stack, where they are resolved in LIFO order (most recent block is freed first)
Heap := section of memory used for dynamic memory allocation(lives until we explicitly deallocate it). Allocation dealt with at run time. Allocate/free a block at any time.
main() := should be at bottom of stack, stack grows up.
When a function is called, it is added on top of the stack. Function parameters are “passed by value”, meaning program first gets value and copies value into a new space for parameters.(thus, there are 2 separate variables that exist in different stack frames)
malloc() := used for dynamic memory allocation
free() := used to deallocate memory
 
int *set_i() {
    int i = 5;
    return &i; //Warning: returning variable from stack that’s only available within function
}
Memory allocated on the stack is deallocated after function exits.
 
Can allocate memory within functions using malloc()
void *malloc(size_t size);  := allocates size bytes of memory on the heap until programmer explicitly deallocates it. returns a void pointer to the memory address. Note: pointers store the type of the information for which it points to.(imp. for pointer arithmetic and to traverse array)
size_t := the type returned by sizeof(), typically unsigned int
 
int *i_pt = malloc(sizeof(int)); #type of pointer specifies how pointer will be used
 
ex1. int *squares_to_10 = squares(10); #holds address of first elements in array. statement #just allocates space for pointer, not for the array itself
int *squares(int max_val) {
    int *result = malloc(max_val * sizeof(int)); #allocates space for array itself on the heap
    for (int i=1; i <= max_val; i++) {
        result[i-1] = i * i;
    }
}
memory leak := memory allocated to the heap with no pointer to it.
out-of-memory error: ENOMEM
 
void free(void *ptr); #
#takes a single argument pointer to a block of memory stored on the heap (by a call to malloc) and returns the address to the system managing the memory for your program so it can be reallocated for a different purpose. 
#free doesn’t reset the values in the block of memory being freed. Tells memory management the address can be repurposed. (called a dangling pointer)
 
Q? Video 4, why does changing the order of the lines *arr_mater = malloc(sizeof(int) *3); and int* arr = *arr_matey; change the outcome?
#if we want to modify a variable of type int * within a function, can’t have parameter int * because we will modify the local variable.
void helper(int **arr_matey) { #pass a pointer to our pointer so we can modify the pointer. 
   *arr_matey = malloc(sizeof(int) * 3);
 
   int *arr = *arr_matey; //can’t have this line above the malloc line because then we will be creating a local variable and not modifying the correct array.
   arr[0] = 18;
   arr[1] = 21;
   arr[2] = 23;
}
 
int main() {
    int *data;
    helper(&data); #always pass in address of variable we want to modify
    free(data)
}
 
 
 
 
 
 
 
 
 
 
Create nested arrays top-down. 
int **pointers = malloc(sizeof(int*)*2);
 
NOTE: don’t dereference if you want to assign malloc after declaration
ex. pointers = malloc(sizeof(int*)*2); //pointers is NOT dereferenced because malloc allocates room and then sets the pointer to point to that address.
 
Allocate subarrays individually
pointers[0] = malloc(sizeof(int));
pointers[1] = malloc(sizeof(int)*3);
//set values
*pointers[0] = 55; \\equivalently, pointers[0][0] = 55;
 
free() := release specified block of memory back to system
Free bottom-up. (typically each malloc call should have a corresponding free call)
free(pointers[0]);
free(pointers[1]);
free(pointers);
Memory array
 
Buffer := anything close to 0 used as a buffer for failure(uninitialized variable will point to 0, seg fault)
Code region := compiled code stored here, close to, but not at 0
Global region := “global” variables stored outside of functions. not connected to any particular function. Also stores string literals.
Heap region := dynamically allocated variables (malloc (memory allocation)). (grows down)
<- file buffer may be in middle
Stack region := most recent function call at the top of stack (in a frame). removed in LIFO order, when removed, frees stack area it was in. (grows up)
OS region := can’t be accessed by normal programs (one of the ways to get a seg fault)
 
 
 
 
 
Strings := not a new data type in C. Char array that contains the null character (\0) to mark the end of the char array. Null character is never displayed in a string.
char text[20]; #char array of 20 elements with indices 0 to 19
text[0] = ‘h’;
text[1] = ‘e’;
text[2] = ‘l’;
text[3] = ‘l’;
text[4] = ‘o’;    
text[5] = ‘\0’;
char text[20] = {‘h’,’e’,’l’,’l’,’o’,’\0’}; //all char’s after null char are set to null char
char text[20] = “hello”; //abbreviation for array initialization before. NOTE: must be double 
quoted
#All of the above are equivalent.
arrays are of fixed size
must allocate space for \0 char or compiler can’t add it
rest of array chars are null
can change values (ex text[2]=’h’;)
sizeof(text) #gives number of bytes occupied by array i.e 20
 
char text[] = “hello”; //initializes fixed size array with just enough room for char’s and one null 
char. NOTE: Not a string literal!
 
 
String literal := immutable constant (gives bus error if we try to modify). type is char *
char *text1=”hello”; #text1 is a pointer to first char of string literal, not an array!
 
size_t strlen(const char *s);
strlen(weekday); #returns length of string. counts chars before null char. 
 
sizeof() := size of a variable/datatype measured in the number of char memory units required for that type. 
    NOTE: sizeof(~) is calculated at compile time and usually isn’t useful (especially if length of array isn’t known at compile time)
 
Copy := overwrite what was there
char *strcpy(char *s1, const char *s2); #UNSAFE
copies the char’s from s2 into the beginning of s1. s1 isn’t required to be a string (since s2 overwrites it). If s1 is too small to fit s2, different compilers handle it in different ways.
 
char *strncpy(char *s1, const char *s2,int n); USUALLY SAFE
n := max number of char’s s1 can hold (including null char)
NOTE: strncpy is UNSAFE if you don’t explicitly add null char after operation
ex.
strncpy(s1, s2,  sizeof(s1));
s1[9] = '\0';
Concatenate/Appending := add s2 string to the end of what was previously at the end of another string s1.
char *strcat(char *s1, const char *s2); #UNSAFE
NOTE: s1 AND s2 must be strings prior to calling strcat
Add s2 to the end of s1(starting at the first null char). 
 
char *strncat(char *s1, const char *s2,int n); #SAFE ALWAYS
n := number of characters NOT including null char that can be copied from s2 to s1.
strncat ALWAYS adds null terminator to s1. SAFE
 
Searching through strings
 
Search for a char 
char *strchr(const char *s, int c);
s := string to search
c := char to search for in the string
searches for the char from left to right in the string. returns a pointer to the pointer if it was found, else returns NULL.
Can find the index by pointer arithmetic. (Pointer to char - s1)
 
char *strstr(const char *s1, const char *s2);
Searches string s1 for the first occurrence of s2.  If s2 is found, returns pointer to char of s1 that begins the first match. Else returns NULL.
 
Arrays aggregate values of a single type into one structure.
Structs and Union
 
 aggregate data when values aren’t the same type
ex. 
 
 
 
array
structure
data of same type
yes
not required
declaration details
type number of elements (array [] notation)
types of members (struct keyword)
access via ...
index notation
dot notation
 
