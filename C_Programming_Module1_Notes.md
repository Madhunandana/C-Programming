# 📘 C Programming — Module 1 Complete Notes
### Reference: Reema Thareja — *Computer Fundamentals and Programming in C*

---

## 📋 Syllabus Topics Covered

1. Introduction to C
2. Structure of C Program
3. Files Used in a C Program
4. Compilers
5. Compiling and Executing C Programs
6. Variables & Constants
7. Input/Output Statements in C
8. Operators in C
9. Type Conversion and Typecasting

---

## 1. Introduction to C

C is a **general-purpose, procedural programming language** developed in the early **1970s** by **Dennis Ritchie** at **Bell Laboratories**, USA. It was originally designed to write the **UNIX operating system**.

### 1.1 History of C

| Year | Event |
|------|-------|
| 1967 | BCPL developed by Martin Richards |
| 1970 | B language developed by Ken Thompson |
| 1972 | C developed by Dennis Ritchie at Bell Labs |
| 1989 | ANSI C standard released (C89) |
| 1990 | ISO C standard (C90) |
| 1999 | C99 standard released |
| 2011 | C11 standard released |

### 1.2 Key Characteristics of C

| Feature | Description |
|---------|-------------|
| **High-Level Language** | Supports structured programming with low-level capabilities |
| **32 Keywords** | Compact — only 32 reserved keywords |
| **Function-Oriented** | Encourages modular programming through functions |
| **Loose Typing** | Allows type flexibility (e.g., treating `char` as `int`) |
| **Portable** | Programs compile on various hardware with minimal changes |
| **Pointer Support** | Allows direct memory access using pointers |
| **Efficient & Stable** | Fast execution, ideal for performance-critical applications |
| **Extensible** | Add features through standard and user-defined libraries |
| **Low-Level Support** | Supports bitwise operations and hardware-level programming |

### 1.3 Uses of C

- **System Programming** — Operating systems (UNIX, Linux kernel)
- **Embedded Systems** — Microcontrollers, IoT devices
- **Compilers & Interpreters** — Many language compilers are written in C
- **Database Engines** — MySQL, PostgreSQL
- **Game Engines** — Core game logic and graphics engines
- **Networking** — Network protocols and socket programming

---

## 2. Structure of a C Program

Every C program follows a well-defined structure.

```
┌─────────────────────────────────────────┐
│         Documentation Section           │  ← Comments (author, purpose)
├─────────────────────────────────────────┤
│            Link Section                 │  ← #include <stdio.h>
├─────────────────────────────────────────┤
│          Definition Section             │  ← #define PI 3.14
├─────────────────────────────────────────┤
│        Global Declaration Section       │  ← Global variables & functions
├─────────────────────────────────────────┤
│           main() Function               │  ← Entry point of program
│  {                                      │
│      Variable Declarations              │
│      Executable Statements              │
│      return 0;                          │
│  }                                      │
├─────────────────────────────────────────┤
│       User-Defined Functions            │  ← Custom functions
└─────────────────────────────────────────┘
```

### 2.1 First C Program

```c
/* First C program: Welcome to the world of C */   // Line 1 & 2 — Comment

#include <stdio.h>                                  // Line 3 — Header file

int main()                                          // Line 4 — main function
{                                                   // Line 5 — Opening brace
    printf("Welcome to the world of C.\n");         // Line 6 — Output statement
    return 0;                                       // Line 7 — Return statement
}                                                   // Line 8 — Closing brace
```

**Output:**
```
Welcome to the world of C.
```

### 2.2 Line-by-Line Explanation

| Line | Code | Explanation |
|------|------|-------------|
| 1–2 | `/* ... */` | Multi-line comment — ignored by compiler, used for documentation |
| 3 | `#include <stdio.h>` | Preprocessor directive — includes Standard I/O header file |
| 4 | `int main()` | Entry point of the program; returns an integer to the OS |
| 5 | `{` | Opening curly brace — begins the function block |
| 6 | `printf(...)` | Calls the printf() function to print text to the screen |
| 7 | `return 0;` | Returns 0 to OS — signals successful program execution |
| 8 | `}` | Closing curly brace — ends the function block |

### 2.3 Comments in C

Comments are used to explain code. The compiler **ignores** them completely.

#### Single-Line Comment — `//`

```c
#include <stdio.h>

int main() {
    // This is a single-line comment
    printf("Hello, World!\n");  // This prints a message
    return 0;
}
```

#### Multi-Line Comment — `/* ... */`

```c
#include <stdio.h>

int main() {
    /*
      This is a multi-line comment.
      It can span multiple lines.
      Useful for longer explanations.
    */
    printf("Welcome to C programming!\n");
    return 0;
}
```

> **Why Use Comments?**
> - Explain complex logic
> - Make code readable for others
> - Temporarily disable lines for debugging

---

## 3. Files Used in a C Program

| File Type | Extension | Description |
|-----------|-----------|-------------|
| **Source Code File** | `.c` | Written by programmer; contains functions like `main()` |
| **Header File** | `.h` | Stores function declarations and macros (e.g., `stdio.h`, `math.h`) |
| **Object File** | `.o` / `.obj` | Machine-readable binary code generated after compilation |
| **Executable File** | `.exe` (Win) / `a.out` (Linux) | Final runnable file created by the linker |

### Standard Header Files

| Header File | Purpose |
|-------------|---------|
| `stdio.h` | Standard input/output — `printf()`, `scanf()` |
| `math.h` | Math functions — `sqrt()`, `pow()`, `sin()` |
| `string.h` | String functions — `strlen()`, `strcpy()` |
| `stdlib.h` | Utility functions — `malloc()`, `free()`, `exit()` |
| `ctype.h` | Character functions — `isdigit()`, `toupper()` |

---

## 4. Compilers

A **compiler** is a program that translates the entire C source code (human-readable) into **machine language** (binary) before execution.

### Popular C Compilers

| Compiler | Platform | Notes |
|----------|----------|-------|
| **GCC** (GNU Compiler Collection) | Linux / Mac / Windows | Most widely used, open-source |
| **Turbo C / Borland C** | DOS / Windows | Historical, used in older curricula |
| **MSVC** | Windows | Microsoft Visual C++ |
| **Clang** | Linux / Mac | Modern, fast compiler |
| **Dev-C++** | Windows | IDE bundled with MinGW GCC |

---

## 5. Compiling and Executing C Programs

### Step-by-Step Process

```
 ┌──────────────┐
 │  Write Code  │  → program.c  (Text editor: Notepad, VS Code, vi)
 └──────┬───────┘
        │
        ▼
 ┌──────────────┐
 │   Compile    │  → program.o  (Compiler checks syntax, creates object code)
 └──────┬───────┘
        │
        ▼
 ┌──────────────┐
 │     Link     │  → program.exe  (Linker combines object code + libraries)
 └──────┬───────┘
        │
        ▼
 ┌──────────────┐
 │     Load     │  (Loader puts executable into RAM)
 └──────┬───────┘
        │
        ▼
 ┌──────────────┐
 │   Execute    │  → Output on screen  (CPU runs instructions)
 └──────────────┘
```

### GCC Commands

```bash
# Step 1: Compile source file
gcc program.c -o program

# Step 2: Execute (Linux/Mac)
./program

# Step 2: Execute (Windows)
program.exe

# Compile with warnings enabled (recommended)
gcc -Wall program.c -o program
```

### Example

```c
/* program.c */
#include <stdio.h>

int main() {
    printf("\n Welcome to the world of C \n");
    return 0;
}
```

**Compile & Run:**
```bash
gcc program.c -o program
./program
```

**Output:**
```
 Welcome to the world of C
```

---

## 6. C Tokens — Building Blocks of C

Tokens are the **smallest individual units** in a C program. There are **6 types** of tokens:

```
C TOKENS
├── 1. Keywords
├── 2. Identifiers
├── 3. Constants
├── 4. Strings
├── 5. Operators
└── 6. Special Symbols
```

### 6.1 Keywords (32 Reserved Words)

Keywords have **fixed meaning** and **cannot be used as variable names**.

```
auto      break     case      char      const     continue
default   do        double    else      enum      extern
float     for       goto      if        int       long
register  return    short     signed    sizeof    static
struct    switch    typedef   union     unsigned  void
volatile  while
```

```c
int age = 25;   // 'int' is a keyword — cannot be used as a variable name
```

### 6.2 Identifiers

User-defined names for variables, functions, arrays, etc.

**Rules for Identifiers:**
- Must start with a **letter (A–Z, a–z)** or **underscore `_`**
- Can contain letters, digits (0–9), and underscores
- **Cannot use keywords** as identifiers
- **Case-sensitive** — `age` and `Age` are different
- Should not exceed **31 characters**
- No spaces or commas allowed

```c
int totalMarks = 90;    // Valid — starts with letter
float _salary = 5000;   // Valid — starts with underscore
int 2result;            // INVALID — starts with digit
int return;             // INVALID — 'return' is a keyword
```

### 6.3 Constants

Fixed values that **do not change** during program execution.

#### Integer Constants

```c
int a = 100;     // Decimal (base 10)
int b = 012;     // Octal (starts with 0) → value = 10 in decimal
int c = 0x1F;    // Hexadecimal (starts with 0x) → value = 31
```

#### Floating-Point Constants

```c
float pi = 3.14;
double rate = 2.5e2;   // Exponential: 2.5 × 10² = 250.0
```

#### Character Constants

```c
char ch = 'A';          // Stored as ASCII value 65
char newline = '\n';    // Escape sequence character
```

#### String Constants

```c
printf("Hello, World!");   // "Hello, World!" is a string constant
// Internally stored as: H e l l o , W o r l d ! \0
```

### 6.4 Special Symbols

| Symbol | Meaning |
|--------|---------|
| `{ }` | Block of code (beginning and end) |
| `( )` | Function call or condition |
| `;` | Statement terminator |
| `,` | Separator between variables |
| `#` | Preprocessor directive |
| `[ ]` | Array subscript |
| `*` | Pointer declaration |

### 6.5 Character Set in C

| Category | Characters |
|----------|-----------|
| **Alphabets** | a–z, A–Z |
| **Digits** | 0–9 |
| **Special Characters** | + - * / = < > . , ; : ' " ( ) { } [ ] $ % ! @ # |
| **White Space** | blank, tab `\t`, newline `\n`, carriage return `\r` |

**Escape Sequences:**

| Escape | Meaning |
|--------|---------|
| `\n` | New line |
| `\t` | Horizontal tab |
| `\b` | Backspace |
| `\r` | Carriage return |
| `\\` | Backslash |
| `\'` | Single quote |
| `\"` | Double quote |
| `\0` | Null character |

---

## 7. Variables in C

A **variable** is a named memory location that stores data which can **change** during program execution.

### 7.1 Data Types

| Data Type | Size | Range | Example |
|-----------|------|-------|---------|
| `int` | 4 bytes | –2,147,483,648 to 2,147,483,647 | `int marks = 90;` |
| `float` | 4 bytes | ±3.4 × 10³⁸ (6 decimal places) | `float pi = 3.14;` |
| `double` | 8 bytes | ±1.7 × 10³⁰⁸ (15 decimal places) | `double rate = 2.5e2;` |
| `char` | 1 byte | –128 to 127 | `char grade = 'A';` |
| `void` | 0 bytes | No value | Used in functions |

### 7.2 Declaration and Initialization

**Syntax:**
```c
data_type variable_name;                   // Declaration
data_type variable_name = value;           // Declaration + Initialization
```

**Example:**
```c
int age;                 // Declaration only
int age = 25;            // Declaration + Initialization
float salary = 50000.50;
char grade = 'A';
int a, b, c;             // Multiple declarations
int x = 1, y = 2, z = 3; // Multiple with initialization
```

### 7.3 Types of Variables

| Type | Where Declared | Scope | Lifetime |
|------|---------------|-------|----------|
| **Local** | Inside a function | Only within that function | Until function ends |
| **Global** | Outside all functions | Entire program | Entire program runtime |
| **Static** | With `static` keyword | Same as local | Entire program runtime |
| **External** | With `extern` keyword | Across multiple files | Entire program runtime |

```c
#include <stdio.h>

int x = 100;       // Global variable — accessible everywhere

int main() {
    int y = 50;           // Local variable
    static int z = 0;     // Static variable — retains value between calls

    printf("x = %d, y = %d, z = %d\n", x, y, z);
    z++;
    return 0;
}
```

**Output:**
```
x = 100, y = 50, z = 0
```

### 7.4 sizeof Operator

Returns the **size in bytes** of a data type or variable at compile time.

**Syntax:**
```c
sizeof(data_type)
sizeof(variable_name)
```

**Example:**
```c
#include <stdio.h>

int main() {
    int a = 5;
    printf("Size of int:    %lu bytes\n", sizeof(int));
    printf("Size of float:  %lu bytes\n", sizeof(float));
    printf("Size of double: %lu bytes\n", sizeof(double));
    printf("Size of char:   %lu bytes\n", sizeof(char));
    printf("Size of var a:  %lu bytes\n", sizeof(a));
    return 0;
}
```

**Output:**
```
Size of int:    4 bytes
Size of float:  4 bytes
Size of double: 8 bytes
Size of char:   1 bytes
Size of var a:  4 bytes
```

---

## 8. Input / Output Statements in C

C provides standard I/O functions through the `<stdio.h>` header file.

### 8.1 printf() — Output Function

Used to **display** text or variable values on the screen.

**Syntax:**
```c
printf("format string", variable1, variable2, ...);
```

**Example:**
```c
#include <stdio.h>

int main() {
    int age = 25;
    float salary = 50000.50;
    char grade = 'A';

    printf("Age: %d\n", age);
    printf("Salary: %.2f\n", salary);
    printf("Grade: %c\n", grade);
    printf("Name: %s\n", "Alice");
    return 0;
}
```

**Output:**
```
Age: 25
Salary: 50000.50
Grade: A
Name: Alice
```

### 8.2 scanf() — Input Function

Used to **read** input from the keyboard.

**Syntax:**
```c
scanf("format string", &variable1, &variable2, ...);
```

> ⚠️ **Note:** The `&` (address-of) operator is **required** before variable names in `scanf()`.

**Example:**
```c
#include <stdio.h>

int main() {
    int age;
    float salary;
    char name[50];

    printf("Enter your name: ");
    scanf("%s", name);         // No & needed for strings/arrays

    printf("Enter age: ");
    scanf("%d", &age);

    printf("Enter salary: ");
    scanf("%f", &salary);

    printf("Name: %s, Age: %d, Salary: %.2f\n", name, age, salary);
    return 0;
}
```

**Output:**
```
Enter your name: Alice
Enter age: 25
Enter salary: 50000.50
Name: Alice, Age: 25, Salary: 50000.50
```

### 8.3 Format Specifiers

| Specifier | Data Type | Example |
|-----------|-----------|---------|
| `%d` or `%i` | Integer | `printf("%d", 42)` → `42` |
| `%f` | Float | `printf("%f", 3.14)` → `3.140000` |
| `%lf` | Double | `printf("%lf", 3.14159)` |
| `%c` | Character | `printf("%c", 'A')` → `A` |
| `%s` | String | `printf("%s", "Hello")` → `Hello` |
| `%o` | Octal | `printf("%o", 8)` → `10` |
| `%x` | Hexadecimal | `printf("%x", 255)` → `ff` |
| `%X` | Hexadecimal (uppercase) | `printf("%X", 255)` → `FF` |
| `%e` | Scientific notation | `printf("%e", 2500.0)` → `2.500000e+03` |
| `%u` | Unsigned integer | Non-negative integers |
| `%lu` | Unsigned long | Used with `sizeof` |

### 8.4 printf() Formatting Options

```c
float c = 98.7654;

printf("%d", 1234);           // Output: 1234
printf("%6d", 1234);          // Output:   1234  (right-aligned, width 6)
printf("%-6d", 1234);         // Output: 1234    (left-aligned)
printf("%06d", 1234);         // Output: 001234  (zero-padded, width 6)
printf("%7.2f", c);           // Output:   98.77  (width 7, 2 decimals)
printf("%-7.2f", c);          // Output: 98.77   (left-justified)
printf("%09.2f", 209.45);     // Output: 000209.45
printf("%e", c);              // Output: 9.876540e+01
printf("%g", c);              // Output: 98.7654  (shorter of %e or %f)
```

---

## 9. Operators in C

An **operator** is a symbol that instructs the compiler to perform a specific operation.

### 9.1 Arithmetic Operators

| Operator | Description | Example (a=10, b=3) | Result |
|----------|-------------|---------------------|--------|
| `+` | Addition | `a + b` | `13` |
| `-` | Subtraction | `a - b` | `7` |
| `*` | Multiplication | `a * b` | `30` |
| `/` | Division | `a / b` | `3` (integer division) |
| `%` | Modulus (remainder) | `a % b` | `1` |

```c
#include <stdio.h>

int main() {
    int a = 10, b = 3;
    printf("Sum:       %d\n", a + b);   // 13
    printf("Diff:      %d\n", a - b);   // 7
    printf("Product:   %d\n", a * b);   // 30
    printf("Quotient:  %d\n", a / b);   // 3
    printf("Remainder: %d\n", a % b);   // 1
    return 0;
}
```

**Output:**
```
Sum:       13
Diff:      7
Product:   30
Quotient:  3
Remainder: 1
```

### 9.2 Relational Operators

Used to **compare** two values. Returns `1` (true) or `0` (false).

| Operator | Description | Example (a=10, b=5) | Result |
|----------|-------------|---------------------|--------|
| `==` | Equal to | `a == b` | `0` (false) |
| `!=` | Not equal to | `a != b` | `1` (true) |
| `>` | Greater than | `a > b` | `1` (true) |
| `<` | Less than | `a < b` | `0` (false) |
| `>=` | Greater than or equal | `a >= b` | `1` (true) |
| `<=` | Less than or equal | `a <= b` | `0` (false) |

```c
#include <stdio.h>

int main() {
    int a = 10, b = 5;
    printf("a == b : %d\n", a == b);   // 0
    printf("a != b : %d\n", a != b);   // 1
    printf("a > b  : %d\n", a > b);    // 1
    printf("a < b  : %d\n", a < b);    // 0
    return 0;
}
```

**Output:**
```
a == b : 0
a != b : 1
a > b  : 1
a < b  : 0
```

### 9.3 Logical Operators

Used to **combine** multiple conditions.

| Operator | Name | Description | Example |
|----------|------|-------------|---------|
| `&&` | Logical AND | True only if **both** conditions are true | `(a>0 && b>0)` |
| `\|\|` | Logical OR | True if **at least one** condition is true | `(a>0 \|\| b>0)` |
| `!` | Logical NOT | **Reverses** the condition | `!(a>0)` |

```c
#include <stdio.h>

int main() {
    int a = 10, b = 5;

    if (a > 0 && b > 0)
        printf("Both are positive\n");

    if (a > 100 || b > 0)
        printf("At least one condition true\n");

    if (!(a < 0))
        printf("a is not negative\n");

    return 0;
}
```

**Output:**
```
Both are positive
At least one condition true
a is not negative
```

### 9.4 Unary Operators

Operate on a **single operand**.

| Operator | Name | Example | Description |
|----------|------|---------|-------------|
| `++` | Increment | `a++` or `++a` | Increases value by 1 |
| `--` | Decrement | `a--` or `--a` | Decreases value by 1 |
| `-` | Unary Minus | `-a` | Negates the value |

**Pre vs Post Increment:**
```c
#include <stdio.h>

int main() {
    int a = 5;

    printf("a++  = %d\n", a++);  // Prints 5, then increments → a = 6
    printf("After: %d\n", a);    // Prints 6

    printf("++a  = %d\n", ++a);  // Increments first → a = 7, then prints 7
    printf("After: %d\n", a);    // Prints 7

    return 0;
}
```

**Output:**
```
a++  = 5
After: 6
++a  = 7
After: 7
```

### 9.5 Conditional (Ternary) Operator

Shorthand for `if-else`.

**Syntax:**
```c
condition ? expression_if_true : expression_if_false;
```

**Example:**
```c
#include <stdio.h>

int main() {
    int a = 10, b = 20;
    int max = (a > b) ? a : b;
    printf("Maximum = %d\n", max);

    // Even or Odd check
    int n = 7;
    printf("%d is %s\n", n, (n % 2 == 0) ? "Even" : "Odd");

    return 0;
}
```

**Output:**
```
Maximum = 20
7 is Odd
```

### 9.6 Bitwise Operators

Operate on **binary representation** of integers.

| Operator | Name | Description | Example (a=5=0101, b=3=0011) |
|----------|------|-------------|-------------------------------|
| `&` | Bitwise AND | 1 only if both bits are 1 | `5 & 3 = 1` (0001) |
| `\|` | Bitwise OR | 1 if at least one bit is 1 | `5 \| 3 = 7` (0111) |
| `^` | Bitwise XOR | 1 if bits differ | `5 ^ 3 = 6` (0110) |
| `~` | Bitwise NOT | Flips all bits | `~5 = -6` |
| `<<` | Left Shift | Shifts bits left (×2) | `5 << 1 = 10` |
| `>>` | Right Shift | Shifts bits right (÷2) | `5 >> 1 = 2` |

```c
#include <stdio.h>

int main() {
    int a = 5;    // Binary: 0101
    int b = 3;    // Binary: 0011

    printf("a & b  = %d\n", a & b);    // AND  = 0001 = 1
    printf("a | b  = %d\n", a | b);    // OR   = 0111 = 7
    printf("a ^ b  = %d\n", a ^ b);    // XOR  = 0110 = 6
    printf("~a     = %d\n", ~a);        // NOT  = -6
    printf("a << 1 = %d\n", a << 1);   // Left shift = 1010 = 10
    printf("a >> 1 = %d\n", a >> 1);   // Right shift = 0010 = 2
    return 0;
}
```

**Output:**
```
a & b  = 1
a | b  = 7
a ^ b  = 6
~a     = -6
a << 1 = 10
a >> 1 = 2
```

### 9.7 Assignment Operators

| Operator | Example | Equivalent to |
|----------|---------|---------------|
| `=` | `a = 10` | `a = 10` |
| `+=` | `a += 5` | `a = a + 5` |
| `-=` | `a -= 3` | `a = a - 3` |
| `*=` | `a *= 2` | `a = a * 2` |
| `/=` | `a /= 4` | `a = a / 4` |
| `%=` | `a %= 3` | `a = a % 3` |

```c
#include <stdio.h>

int main() {
    int a = 10;
    printf("Initial a = %d\n", a);

    a += 5;  printf("a += 5  → a = %d\n", a);   // 15
    a -= 3;  printf("a -= 3  → a = %d\n", a);   // 12
    a *= 2;  printf("a *= 2  → a = %d\n", a);   // 24
    a /= 4;  printf("a /= 4  → a = %d\n", a);   // 6
    a %= 4;  printf("a %= 4  → a = %d\n", a);   // 2

    return 0;
}
```

**Output:**
```
Initial a = 10
a += 5  → a = 15
a -= 3  → a = 12
a *= 2  → a = 24
a /= 4  → a = 6
a %= 4  → a = 2
```

### 9.8 Operator Precedence & Associativity

When multiple operators appear in an expression, **precedence** decides which is evaluated first.

| Priority | Operator Type | Operators | Associativity |
|----------|--------------|-----------|---------------|
| 1 (Highest) | Postfix | `()` `[]` `->` `.` | Left → Right |
| 2 | Unary | `+` `-` `++` `--` `!` `sizeof` | Right → Left |
| 3 | Multiplicative | `*` `/` `%` | Left → Right |
| 4 | Additive | `+` `-` | Left → Right |
| 5 | Relational | `<` `<=` `>` `>=` | Left → Right |
| 6 | Equality | `==` `!=` | Left → Right |
| 7 | Bitwise AND | `&` | Left → Right |
| 8 | Bitwise XOR | `^` | Left → Right |
| 9 | Bitwise OR | `\|` | Left → Right |
| 10 | Logical AND | `&&` | Left → Right |
| 11 | Logical OR | `\|\|` | Left → Right |
| 12 | Conditional | `?:` | Right → Left |
| 13 (Lowest) | Assignment | `=` `+=` `-=` etc. | Right → Left |

**Example:**
```c
#include <stdio.h>

int main() {
    int a = 10, b = 5, c = 2;

    int result = a + b * c;          // b*c evaluated first (higher precedence)
    printf("10 + 5 * 2 = %d\n", result);    // 20, not 30

    int result2 = (a + b) * c;       // Parentheses override precedence
    printf("(10 + 5) * 2 = %d\n", result2); // 30

    return 0;
}
```

**Output:**
```
10 + 5 * 2 = 20
(10 + 5) * 2 = 30
```

> 💡 **Tip:** Always use parentheses `()` to make the order of evaluation clear and avoid bugs.

---

## 10. Type Conversion and Typecasting in C

**Type conversion** refers to changing a value from one data type to another.

### 10.1 Implicit Type Conversion (Automatic)

The compiler **automatically** converts lower data types to higher data types to prevent data loss.

**Type Hierarchy (lower → higher):**
```
char → int → unsigned int → long → float → double → long double
```

**Example:**
```c
#include <stdio.h>

int main() {
    int a = 10;
    float b = 5.5;

    float c = a + b;   // 'a' (int) is automatically promoted to float
    printf("Result: %.2f\n", c);

    // Integer + float = float result
    int x = 5;
    double y = 2.0;
    double z = x + y;   // x is promoted to double
    printf("z = %.2f\n", z);

    return 0;
}
```

**Output:**
```
Result: 15.50
z = 7.00
```

### 10.2 Explicit Type Casting

The programmer **manually** forces conversion using a cast operator.

**Syntax:**
```c
(data_type) expression;
```

**Example 1 — Integer Division Problem:**
```c
#include <stdio.h>

int main() {
    int a = 5, b = 2;

    // Without casting — integer division (loses decimal)
    printf("Without cast: %d\n", a / b);       // Output: 2

    // With casting — float division
    float result = (float)a / b;
    printf("With cast:    %.2f\n", result);     // Output: 2.50

    return 0;
}
```

**Output:**
```
Without cast: 2
With cast:    2.50
```

**Example 2 — float to int (data loss):**
```c
#include <stdio.h>

int main() {
    float f = 9.99;
    int i = (int)f;      // Decimal part is truncated (not rounded)
    printf("float: %.2f → int: %d\n", f, i);
    return 0;
}
```

**Output:**
```
float: 9.99 → int: 9
```

**Example 3 — char to int:**
```c
#include <stdio.h>

int main() {
    char ch = 'A';
    int ascii = (int)ch;   // Get ASCII value of 'A'
    printf("Character: %c → ASCII: %d\n", ch, ascii);
    return 0;
}
```

**Output:**
```
Character: A → ASCII: 65
```

### 10.3 Comparison: Implicit vs Explicit

| Feature | Implicit Conversion | Explicit Casting |
|---------|-------------------|-----------------|
| Done by | Compiler automatically | Programmer manually |
| Also called | Automatic / Widening | Typecasting / Explicit |
| Control | No programmer control | Full programmer control |
| Risk | Safe (lower → higher) | Can cause data loss |
| Syntax | No special syntax | `(data_type) expression` |
| Example | `int + float → float` | `(float) int_var / b` |

### 10.4 Common Pitfalls

```c
#include <stdio.h>

int main() {
    // Pitfall 1: Integer division without casting
    int a = 7, b = 2;
    float wrong = a / b;          // Integer division happens FIRST → 3
    float correct = (float)a / b; // Cast first, then divide → 3.5
    printf("Wrong:   %.1f\n", wrong);    // 3.0
    printf("Correct: %.1f\n", correct);  // 3.5

    // Pitfall 2: Float to int truncates (not rounds)
    float x = 3.9;
    int truncated = (int)x;       // 3, NOT 4
    printf("3.9 → int: %d\n", truncated);  // 3

    return 0;
}
```

**Output:**
```
Wrong:   3.0
Correct: 3.5
3.9 → int: 3
```

---

## 📝 Quick Reference — Important Programs

### Program 1: Simple Calculator

```c
#include <stdio.h>

int main() {
    float a, b;
    printf("Enter two numbers: ");
    scanf("%f %f", &a, &b);

    printf("Sum:        %.2f\n", a + b);
    printf("Difference: %.2f\n", a - b);
    printf("Product:    %.2f\n", a * b);

    if (b != 0)
        printf("Quotient:   %.2f\n", a / b);
    else
        printf("Division by zero not allowed!\n");

    return 0;
}
```

### Program 2: Swap Two Numbers

```c
#include <stdio.h>

int main() {
    int a, b, temp;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    temp = a;
    a = b;
    b = temp;

    printf("After swap: a = %d, b = %d\n", a, b);
    return 0;
}
```

### Program 3: Find Maximum of Two Numbers (Ternary)

```c
#include <stdio.h>

int main() {
    int a, b;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    int max = (a > b) ? a : b;
    printf("Maximum = %d\n", max);
    return 0;
}
```

### Program 4: Area of a Circle

```c
#include <stdio.h>

#define PI 3.14159

int main() {
    float radius, area;
    printf("Enter radius: ");
    scanf("%f", &radius);

    area = PI * radius * radius;
    printf("Area of circle = %.2f\n", area);
    return 0;
}
```

### Program 5: Size of All Data Types

```c
#include <stdio.h>

int main() {
    printf("Data Type Sizes:\n");
    printf("int:           %lu bytes\n", sizeof(int));
    printf("float:         %lu bytes\n", sizeof(float));
    printf("double:        %lu bytes\n", sizeof(double));
    printf("char:          %lu bytes\n", sizeof(char));
    printf("long int:      %lu bytes\n", sizeof(long int));
    printf("unsigned int:  %lu bytes\n", sizeof(unsigned int));
    return 0;
}
```

---

## 🔑 Key Points to Remember

1. Every C program must have a `main()` function — it is the **entry point**.
2. Every statement in C ends with a **semicolon `;`**.
3. C is **case-sensitive** — `Age` and `age` are different variables.
4. Use `#include <stdio.h>` for `printf()` and `scanf()`.
5. The `&` (address-of) operator is **mandatory** in `scanf()` for basic variables.
6. Integer division truncates the decimal — use casting `(float)` when needed.
7. Comments are for humans — the compiler ignores them completely.
8. Keywords cannot be used as variable or function names.
9. Use `\n` inside `printf()` strings to move to a new line.
10. `sizeof()` returns the size in **bytes** of a data type or variable.

---

*📚 Reference: Reema Thareja — Computer Fundamentals and Programming in C*  
*Module 1 | C Programming Online Course*
