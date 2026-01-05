---
icon: blanket
---

# Theory of C programming and basics

#### Part 1: C Programming Fundamentals

## 1.1 The C Language and Compilation

Understanding a programming language's core identity and its compilation process is a crucial first step for any developer. This knowledge is foundational to effective debugging, performance optimization, and grasping how human-readable code is ultimately translated into instructions that a machine can execute. The following questions explore these essential concepts.

* What is C / What is C programming? C is a powerful, general-purpose, procedural programming language developed in the early 1970s by Dennis Ritchie at Bell Labs. It's considered a mid-level language because it combines features of high-level languages (offering abstraction and readability) with the functionality of low-level assembly languages (allowing for direct memory manipulation). Its efficiency, performance, and flexibility have made it a cornerstone of software development for decades.
* What is a compiler? A compiler is a special program that translates source code written in a high-level programming language (like C or Java) into a lower-level language, typically machine code or object code, that a computer's processor can directly understand and execute. This translation process is done all at once, creating a standalone executable file.
* What is an interpreter? An interpreter is another type of program that translates and executes source code. Unlike a compiler, an interpreter reads the source code line by line, translating and executing each line immediately. It does not produce a separate executable file.

### 1.1.2 Difference between Compiler and Interpreter

| Feature           | Compiler                                                               | Interpreter                                                               |
| ----------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Process           | Translates the entire program at once before execution.                | Translates and executes the program line by line.                         |
| Output            | Creates a standalone executable file (e.g., `.exe`, `.out`).           | Does not create an executable file.                                       |
| Speed             | Execution is generally faster because the translation is already done. | Execution is generally slower due to real-time, line-by-line translation. |
| Error Checking    | Reports all syntax errors at the end of the compilation phase.         | Stops execution as soon as it encounters the first error.                 |
| Example Languages | C, C++, Rust                                                           | Python, JavaScript, Ruby                                                  |

* Is C a compiled language or not? Yes, C is a compiled language. You must run the C source code through a C compiler to create an executable file before the program can be run.
* What is compilation? Compilation is the multi-stage process of converting source code written in a high-level language into machine-executable code. For C, this process typically involves four main steps:
  1. Preprocessing: The preprocessor handles directives (lines starting with `#`), such as including header files (`#include`) and expanding macros (`#define`).
  2. Compilation: The compiler translates the preprocessed code into assembly code specific to the target processor architecture.
  3. Assembly: The assembler converts the assembly code into machine-readable object code, storing it in an object file (e.g., `.o` or `.obj`).
  4. Linking: The linker combines the object code from your program with code from any necessary libraries (like the standard C library) to create a single, complete executable file.
* What are the uses of C programming? C's performance and low-level capabilities make it ideal for a wide range of applications, including:
  * Operating Systems: Core components of Windows, Linux, and macOS are written in C.
  * Embedded Systems: It's used to program microcontrollers in devices like cars, appliances, and industrial equipment.
  * System Software: Compilers, assemblers, and device drivers are often written in C.
  * Databases: Major databases like Oracle and MySQL use C for their core engines.
  * Game Development: C and its successor, C++, are widely used for developing high-performance game engines.
* Is C platform dependent/independent? C is considered platform dependent. While the C language itself is standardized and portable (meaning you can write C code that compiles on many systems), the compiled executable file is not. A program compiled on a Windows machine will not run on a Linux machine or a Mac without being recompiled specifically for that platform's architecture and operating system.

With a grasp of how a C program comes to life, we can now turn to the building blocks of the language: its syntax and data types.

## 1.2 Core Syntax, Data Types, and Operators

The syntax, data types, and operators of a language are its basic grammar. Mastering these elements is the first step toward writing code that is not only functional but also efficient and readable. They provide the rules for defining data and performing operations on it.

* What is a variable? A variable is a named storage location in memory that holds a value. This value can be changed during program execution. In C, every variable must be declared with a specific data type, which determines the size and layout of the variable's memory and the range of values it can store.
* What is an identifier? An identifier is the name given to a user-defined entity in a program, such as a variable, function, array, or structure. Identifiers must follow certain rules, such as starting with a letter or an underscore and consisting of only letters, numbers, and underscores.
* What is the difference between an identifier and a variable? This is a common point of confusion. The key distinction is that a variable is a specific _type_ of entity (a memory location), while an identifier is the _name_ you give to an entity.
* Think of it this way: all variables have identifiers, but not all identifiers refer to variables. For example, a function name is an identifier, but it is not a variable.
  * `int userAge;` // `userAge` is an identifier for a variable.
  * `void calculateSum();` // `calculateSum` is an identifier for a function.
* What are keywords? Keywords are reserved words in the C language that have a special, predefined meaning for the compiler. These words cannot be used as identifiers (e.g., for variable or function names). Examples include `int`, `if`, `else`, `for`, `while`, and `return`.
* What are data types? A data type specifies the type of data that a variable can hold. It informs the compiler how much memory to allocate for the variable and how to interpret the bits stored in that memory. Examples include `int` for integers, `char` for characters, and `float` for floating-point numbers.
* What are primitive and non-primitive data types?
  * Primitive Data Types: These are the fundamental data types built directly into the C language. They represent single values. The main primitive types are `int` (integers), `char` (characters), `float` (single-precision floating-point numbers), `double` (double-precision floating-point numbers), and `void` (valueless).
  * Non-Primitive (or Derived) Data Types: These types are derived from primitive data types and are more complex. They can store collections of values or more structured data. Examples include arrays, pointers, structures, and unions.
* What is the difference between float and double? Both `float` and `double` are used to store floating-point (decimal) numbers, but they differ in precision and storage size.

| Feature   | `float`                                                               | `double`                                                                                       |
| --------- | --------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Size      | Typically 4 bytes                                                     | Typically 8 bytes                                                                              |
| Precision | Single-precision (approx. 6-7 decimal digits)                         | Double-precision (approx. 15-16 decimal digits)                                                |
| Use Case  | Suitable when memory is a concern and high precision is not required. | Default choice for floating-point math due to higher precision; less prone to rounding errors. |

* What are the different types of operators? An operator is a symbol that tells the compiler to perform a specific mathematical, relational, or logical operation. The main types include:
  * Arithmetic Operators: Used for mathematical calculations (`+`, `-`, `*`, `/`, `%` modulus).
  * Assignment Operators: Used to assign values to variables (`=`, `+=`, `-=`, `*=`, `/=`).
  * Relational Operators: Used to compare two values (`==`, `!=`, `>`, `<`, `>=`, `<=`).
  * Logical Operators: Used to combine conditional statements (`&&` AND, `||` OR, `!` NOT).
  * Increment/Decrement Operators: Used to increase or decrease a value by one (`++`, `--`).
  * Bitwise Operators: Used for operations on individual bits of data (`&`, `|`, `^`, `~`, `<<`, `>>`).
  * Ternary (Conditional) Operator: A shorthand for an `if-else` statement (`? :`).
* What is the difference between = and == (single equal and double equal)?
  * `=` (Assignment Operator): This operator is used to _assign_ the value on the right to the variable on the left.
  * `==` (Equality Operator): This is a relational operator used to _compare_ two values to see if they are equal. It returns a boolean result (true/1 or false/0).
* What is a ternary operator? The ternary operator (or conditional operator) is a shorthand for a simple `if-else` statement. It takes three operands: a condition, a value to return if the condition is true, and a value to return if the condition is false. Syntax: `condition ? value_if_true : value_if_false;`
* What are arithmetic assignment operators? These are shorthand operators that combine an arithmetic operation with an assignment operation. They provide a more concise way to modify a variable's value.
  * `a += b;` is equivalent to `a = a + b;`
  * `a -= b;` is equivalent to `a = a - b;`
  * `a *= b;` is equivalent to `a = a * b;`
  * `a /= b;` is equivalent to `a = a / b;`
* What is pre-increment and post-increment? Both `++` operators increase the value of a variable by one, but they differ in _when_ the value is updated relative to its use in an expression.
  * Pre-increment (`++var`): The value of the variable is incremented _first_, and then the new value is used in the expression.
  * Post-increment (`var++`): The original value of the variable is used in the expression _first_, and then the value is incremented.
* What are escape sequences / escape characters? An escape sequence is a sequence of characters that does not represent itself when used inside a string literal or character. It is preceded by a backslash (`\`) and is used to represent non-printable characters or characters that have a special meaning.
  * `\n`: Newline
  * `\t`: Tab
  * `\\`: Backslash
  * `\"`: Double quote
  * `\'`: Single quote
* What is the `sizeof` operator? The `sizeof` operator is a compile-time operator that returns the size, in bytes, of a variable or a data type. It is useful for understanding memory allocation and for working with dynamic memory.
* (Note: `%zu` is the correct format specifier for the `size_t` type returned by `sizeof`.)

Understanding how to declare variables and manipulate data naturally leads to the need to control the flow of a program's execution.

## 1.3 Control Flow: Loops and Conditional Statements

Control flow structures are the decision-making components of a program. Conditional statements (like `if-else`) and loops allow developers to dictate execution paths based on specific conditions, repeat actions efficiently, and create dynamic, responsive logic rather than having code that only executes line-by-line.

* What are condition statements? (e.g., if and if-else) Conditional statements allow a program to execute different blocks of code based on whether a certain condition is true or false.
  * `if` statement: Executes a block of code only if the specified condition is true.
  * `if-else` statement: Executes one block of code if the condition is true and a different block if it is false.
  * `if-else if-else` ladder: Used to test a series of conditions in order.
  * `switch` statement: Allows a variable to be tested for equality against a list of values (cases).
* What are loops and what are the different types of loops? / Explain `for`, `while`, and `do-while` loops. / What is the difference between a `for` loop and a `while` loop? A loop is a control flow structure that allows a block of code to be executed repeatedly as long as a certain condition is met.
* The main types of loops in C are:
  1. `for` loop: Typically used when the number of iterations is known beforehand. It combines initialization, condition checking, and increment/decrement into a single line.
  2. `while` loop: Used when the number of iterations is unknown. It checks the condition _before_ executing the loop body. If the condition is false initially, the loop body never runs.
  3. `do-while` loop: Similar to a `while` loop, but it checks the condition _after_ executing the loop body. This guarantees that the loop body will run at least once.
* Key Difference between `for` and `while`: The primary difference is syntax and typical use case. A `for` loop is more structured for a known number of iterations, keeping the loop control variables (initialize, condition, update) together. A `while` loop is more flexible and is often used when the loop's continuation depends on an external event or a condition that doesn't follow a simple numeric progression.
* What is an entry-controlled loop vs. an exit-controlled loop? This distinction is based on when the loop's condition is checked.
  * Entry-Controlled Loop: The condition is checked _before_ the loop body is executed. If the condition is false, the body is never entered. `for` and `while` loops are entry-controlled.
  * Exit-Controlled Loop: The condition is checked _after_ the loop body is executed. This means the loop body is guaranteed to execute at least once. The `do-while` loop is an exit-controlled loop.
* What are jump statements? Jump statements are used to transfer control of the program to another part of the code unconditionally. They are used to exit loops, skip iterations, or move to other parts of a function. The main jump statements in C are `break`, `continue`, `goto`, and `return`.
* What is the function of `break` and `continue`?
  * `break`: When encountered inside a loop or a `switch` statement, `break` immediately terminates the innermost loop or `switch` and transfers control to the statement immediately following it.
  * `continue`: When encountered inside a loop, `continue` skips the rest of the current iteration of the loop body and proceeds to the next iteration.
* What happens in a `switch` case if there is no `break` statement? If a `case` in a `switch` statement does not have a `break`, execution will fall through to the next `case` and execute its code, regardless of whether that next case's value matches the switch variable. This continues until a `break` statement is found or the `switch` block ends. This "fall-through" behavior can be a source of bugs if unintended, but it can also be used intentionally to handle multiple cases with the same block of code.

Once we can control the flow of logic, the next step is to organize that logic into reusable blocks called functions.

## 1.4 Functions and Program Structure

Functions are the primary mechanism for code organization, reusability, and modularity in C. A well-structured program uses functions to break down complex problems into smaller, manageable, and logical units. This approach makes code easier to write, test, and maintain.

* What is a function? A function is a self-contained block of code that performs a specific task. It can be called from other parts of the program to execute that task. Functions can accept input values (called arguments) and can return a value to the part of the code that called them.
* What is the `main` function? The `main` function is a special function in C that serves as the entry point for program execution. When you run a C program, the operating system starts execution from the first line of the `main` function. Every C program must have exactly one `main` function.
* Why do we use `int main()` instead of `char` or `float`? We use `int main()` because the C standard specifies that the `main` function should return an integer value to the operating system. This integer is an exit status or error code. A return value of `0` conventionally signifies that the program executed successfully, while a non-zero value indicates that an error occurred. Other return types like `char` or `float` are not standard and do not align with this system of communicating success or failure to the host environment.
* Can we pass parameters in the `main` function? Yes. The `main` function can accept parameters, which are used to receive command-line arguments when the program is executed from a terminal. The standard signature for this is `int main(int argc, char *argv[])`, where:
  * `argc` (argument count) is an integer that holds the number of command-line arguments.
  * `argv` (argument vector) is an array of character pointers (strings), where each string is one of the arguments passed to the program.
* What is the difference between arguments and parameters? While often used interchangeably, these terms have distinct meanings:
  * A parameter is the variable listed inside the parentheses in a function's definition. It acts as a placeholder for a value that the function will receive.
  * An argument is the actual value that is passed to the function when it is called.
* What does `return` do? The `return` statement terminates the execution of the current function and returns control to the calling function. It can also send a value back to the caller. A function declared with a `void` return type does not return a value and can use `return;` without a value to exit early.
* Why do we use `return 0`? In the `main` function, `return 0;` is used to signal to the operating system that the program has completed its execution successfully. Any other non-zero value typically indicates an error.
* What are the different types of return functions/return types? A function's return type is the data type of the value that the function returns. A function can return any valid C data type, including:
  * Primitive types: `int`, `char`, `float`, `double`.
  * Derived types: Pointers (e.g., `int*`, `char*`).
  * `void`: A special type indicating that the function does not return any value.
* What is Pass by Value vs. Pass By Reference? This describes how arguments are passed to functions.
  * Pass by Value: A _copy_ of the argument's value is passed to the function. Any changes made to the parameter inside the function do not affect the original argument in the calling code. This is the default mechanism in C for non-pointer types.
  * Pass by Reference: The _memory address_ of the argument is passed to the function (using a pointer). This means the function can directly access and modify the original argument's value.
* Can we return an array from a function? No, you cannot directly return an entire array from a function in C. The name of an array often decays to a pointer to its first element, but returning it directly is problematic because arrays passed to functions are local variables and will be destroyed when the function exits.
* The correct way to achieve this is to return a pointer to the array. The array must be allocated in a way that it persists after the function returns, such as using `static` storage or dynamic memory allocation (`malloc`).

This discussion of functions and data passing leads directly to one of the most critical data structures in C: the array.

## 1.5 Working with Arrays

Arrays are a fundamental data structure for storing and managing collections of related, same-type data. Their role is central to solving a wide range of programming problems that involve processing lists, tables, or other groups of items in a structured manner.

* What is an array? An array is a collection of a fixed number of items of the same data type, stored in contiguous memory locations. Each item in the array is called an element, and it can be accessed directly using its numerical index.
* What are the basic concepts of an array?
  * Fixed Size: The size of a standard C array must be a constant integer and is fixed at the time of declaration.
  * Homogeneous Elements: All elements in an array must be of the same data type.
  * Contiguous Memory: Elements are stored side-by-side in memory, allowing for efficient access.
  * Zero-Based Indexing: The first element of the array is at index 0, the second at index 1, and so on.
* What are the different types of arrays?
  * One-Dimensional Array: A simple list of elements.
  * Multi-Dimensional Array: An "array of arrays," used to represent matrices or tables (e.g., a 2D array for a grid).
  * Static Array: An array whose size is fixed at compile time and memory is allocated on the stack.
  * Dynamic Array: An array whose size is determined at runtime, with memory allocated on the heap using functions like `malloc`.
* What is a static array? A static array is an array where the size is specified by a constant integer value at compile time. Its memory is allocated in the data segment or on the stack, depending on where it is declared. Its lifetime is tied to its scope.
* What is a dynamic array? A dynamic array is one whose size is not known until runtime. Memory for a dynamic array is allocated from the heap using memory allocation functions like `malloc`, `calloc`, or `realloc`. The programmer is responsible for freeing this memory using `free()` when it's no longer needed.
* What is a sparse array? A sparse array is an array in which most of the elements have a default value (usually zero). Instead of storing all the elements, which would be inefficient, specialized data structures are used to store only the non-default elements along with their indices.
* What is a multi-dimensional array / 2-dimensional array? A multi-dimensional array is an array with more than one dimension. A 2D array is the most common type, representing a grid or table with rows and columns. It's essentially an array where each element is itself another array. `int matrix[3][4];` // Declares a 2D array with 3 rows and 4 columns.
* How is an array declared? An array is declared by specifying the data type of its elements, its name, and its size in square brackets. Syntax: `dataType arrayName[arraySize];` `int scores[10];` // Declares an integer array named 'scores' that can hold 10 elements.
* How do you find an index value? You don't "find" an index value; you _use_ an index to access the value at a specific position in the array. The index is an integer representing the element's position, starting from 0. `int value = scores[3];` // Accesses the 4th element (at index 3) of the 'scores' array.
* What does the first index of a multidimensional array represent? In a 2D array like `matrix[R][C]`, the first index (`R`) represents the row. The second index (`C`) represents the column. So, `matrix[0]` refers to the first row of the matrix.
* What is the last index value of an array? For an array of size `N`, the last valid index is `N - 1`. This is due to zero-based indexing. For an array declared as `int arr[10];`, the valid indices are 0 through 9, and the last index is 9.

Beyond structuring data, a program must also be able to interact with its environment, which requires tools for input, output, and pre-compilation setup.

## 1.6 Input/Output and Preprocessing

For a program to be interactive and useful, it must be able to communicate with the user and its environment. Preprocessor directives and standard input/output (I/O) functions are the essential tools for this interaction. They allow a program to include external libraries, receive input, display output, and set up its context before compilation even begins.

* What are preprocessor directives? Preprocessor directives are instructions for the C preprocessor, which runs before the actual compilation begins. These directives start with a hash symbol (`#`) and are used for tasks like including files, defining macros, and conditional compilation.
* What are the different types of preprocessor directives?
  * File Inclusion (`#include`): Includes the contents of another file (typically a header file) into the source file.
  * Macro Definition (`#define`, `#undef`): Defines a macro (a fragment of code that is given a name) or undefines it.
  * Conditional Compilation (`#if`, `#ifdef`, `#ifndef`, `#else`, `#elif`, `#endif`): Includes or excludes parts of the code from compilation based on certain conditions.
  * Other Directives (`#error`, `#pragma`): Used to print error messages or provide special instructions to the compiler.
* What is the purpose of `#include <stdio.h>`? This directive tells the preprocessor to include the contents of the standard header file `stdio.h` (Standard Input/Output) into the program. This header file contains the declarations for standard I/O functions like `printf()` and `scanf()`.
* For what are `printf()` and `scanf()` used?
  * `printf()` (print formatted): A standard library function used to send formatted output to the console (standard output). It can print text, variable values, and more, according to a specified format string.
  * `scanf()` (scan formatted): A standard library function used to read formatted input from the console (standard input). It reads characters from the input stream and stores them in variables according to a format string.
* What is a placeholder / format specifier? A format specifier is a code used in formatted I/O functions (like `printf` and `scanf`) that tells the function what type of data to print or read. It starts with a `%` character.
  * `%d`: Integer (`int`)
  * `%f`: Floating-point number (`float`)
  * `%lf`: Double-precision floating-point number (`double`)
  * `%c`: Character (`char`)
  * `%s`: String (character array)
* What are error codes? An error code is a numeric or alphanumeric code that indicates the nature of an error that has occurred in a program. In C, the `main` function returns an integer error code to the operating system. By convention, `0` means success, and any non-zero value indicates a specific type of failure.
* What is type casting? Type casting is a way to explicitly convert a variable from one data type to another. This is done by prefixing the variable with the new data type in parentheses.
