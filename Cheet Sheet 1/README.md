# 🖥️ C Programming Language — Complete Learning Guide

> **Made by your Tutor — SK SAHIL**
> *Freelance AI Developer · Freelance Coding Tutor · Working in 4 Startups · Graduated from German University with Excellence Grade*
> *NYCTA — National Youth Computer Training Academy — "Committed To Build Youth"*

---

## 📌 What is C?

**C** is a **general-purpose, procedural, compiled programming language** developed by **Dennis Ritchie** in **1972** at **Bell Laboratories, USA**. It is considered the **mother of all programming languages** — most modern languages like C++, Java, and Python are influenced by C.

C is **compiled** (converted to machine code before execution), **statically typed** (types declared at compile time), and runs **very close to the hardware**, making it extremely fast and efficient.

```
Source Code (.c) → C Compiler (gcc/mingw) → Machine Code (.exe / .out) → Output
```

> 💡 **History Tip:** *"Dennis Ritchie, 1972, Bell Laboratories, USA — always remember this for your exam."*

---

## 🌍 Where is C Used?

| Domain | Use Case |
|---|---|
| **Operating Systems** | Linux, Windows, Unix kernels are written in C |
| **Embedded Systems** | Microcontrollers, Arduino, IoT devices |
| **System Programming** | Drivers, compilers, assemblers |
| **Game Development** | Game engines at low level |
| **Database Systems** | MySQL, PostgreSQL core |
| **Networking** | Routers, switches firmware |

---

## 🛠️ IDE & Compiler Tools

| Tool | Type | Link |
|---|---|---|
| **VS Code + GCC** | Lightweight editor + compiler | [code.visualstudio.com](https://code.visualstudio.com/) |
| **Code::Blocks** | Dedicated C/C++ IDE | [codeblocks.org](https://www.codeblocks.org/) |
| **Dev-C++** | Beginner-friendly IDE | [sourceforge.net/projects/dev-cpp](https://sourceforge.net/projects/dev-cpp/) |
| **CLion** | Professional C IDE | [jetbrains.com/clion](https://www.jetbrains.com/clion/) |
| **MinGW (GCC)** | Compiler for Windows | [mingw-w64.org](https://www.mingw-w64.org/) |

## 🌐 Online IDE (No Installation Needed)

| Tool | Link |
|---|---|
| **OneCompiler** | [onecompiler.com/c](https://onecompiler.com/c) |
| **Programiz Online** | [programiz.com/c-programming/online-compiler](https://www.programiz.com/c-programming/online-compiler/) |
| **Replit** | [replit.com](https://replit.com/) |
| **Compiler Explorer** | [godbolt.org](https://godbolt.org/) |

## 📚 Official Documentation

- 📖 **W3Schools C Tutorial:** [w3schools.com/c](https://www.w3schools.com/c/)
- 📖 **GeeksForGeeks C:** [geeksforgeeks.org/c-programming-language](https://www.geeksforgeeks.org/c-programming-language/)
- 📖 **TutorialsPoint C:** [tutorialspoint.com/cprogramming](https://www.tutorialspoint.com/cprogramming/)

---

## ⚡ Critical Interview Concepts — Read This First!

> The **most-asked C interview topics**. Know each one with an example.

---

### 🏗️ Program Structure — Every C Program Has This

```c
#include <stdio.h>       // Pre-processor directive — includes standard I/O library
                         // Without this, printf() and scanf() won't work

int main() {             // Program execution ALWAYS starts from main()
    printf("Hello World\n");   // Output function
    return 0;            // 0 means program ran successfully
}
```

> 💡 **Interview Tip:** *"Every C program must have a `main()` function. Execution starts and ends at `main()`. `#include <stdio.h>` is mandatory for using `printf` and `scanf`."*

---

### 📦 Variables & Data Types — Most Asked

A **variable** is a named memory location that stores data. Before using any variable, you must **declare its type**.

```c
int    age    = 22;       // Integer — 2 or 4 bytes — whole numbers
float  pi     = 3.14;     // Float — 4 bytes — decimal numbers
double price  = 99.999;   // Double — 8 bytes — more precise decimals
char   grade  = 'A';      // Char — 1 byte — single character

// Multiple declaration
int a = 10, b = 20, c;   // Valid — c is declared but not initialized

// Constants — value cannot change
const float PI = 3.14159;
```

| Data Type | Size | Format Specifier | Range |
|---|---|---|---|
| `int` | 2 or 4 bytes | `%d` | -32768 to 32767 (2 bytes) |
| `float` | 4 bytes | `%f` | ~6-7 decimal digits |
| `double` | 8 bytes | `%lf` | ~15-16 decimal digits |
| `char` | 1 byte | `%c` | -128 to 127 |
| `long int` | 4 or 8 bytes | `%ld` | larger integer range |

> 💡 **Interview Tip:** *"Variable rules: case-sensitive, must start with letter or `_`, no spaces or special chars except `_`."*

---

### 🔑 Keywords — 32 Reserved Words

Keywords are **reserved words with special meaning** to the compiler. You cannot use them as variable names.

```
auto    break    case    char    const    continue    default    do
double  else     enum    extern  float    for         goto       if
int     long     register return  short   signed      sizeof     static
struct  switch   typedef  union  unsigned void        volatile   while
```

> 💡 **Interview Tip:** *"C has exactly 32 keywords. They are all lowercase."*

---

### 🔧 Operators — Most Conceptual Topic

An **operator** is a symbol that performs an operation on operands.

```c
// In:  a + b
// 'a' and 'b' are OPERANDS
// '+' is the OPERATOR
```

**Operator Precedence (High to Low):**

| Priority | Operator | Example |
|---|---|---|
| 1 (Highest) | `!` (NOT) | `!true` |
| 2 | `*`, `/`, `%` | `5 * 3 / 2` |
| 3 | `+`, `-` | `5 + 3` |
| 4 | `<`, `<=`, `>`, `>=` | `a > b` |
| 5 | `==`, `!=` | `a == b` |
| 6 | `&&` (AND) | `a && b` |
| 7 | `\|\|` (OR) | `a \|\| b` |
| 8 (Lowest) | `=` | `x = 5` |

**Left to Right Associativity** — when operators have same precedence, evaluate left to right:
```
x = 4 * 3 / 6 * 2
  = 12 / 6 * 2     ← left to right
  = 2 * 2
  = 4
```

> 💡 **Interview Tip:** *"`^` is NOT power in C — use `pow(x, y)` from `math.h`. `%` is modulo — only works with integers."*

---

### 🔀 Type Conversion — Implicit vs Explicit

```c
// Implicit (automatic) — compiler does it
int   op int   = int       // 5 / 2 = 2 (truncated!)
int   op float = float     // 5 / 2.0 = 2.5
float op float = float

// Explicit (manual) — you force it — called TYPE CASTING
int a = (int) 1.999999;    // a = 1 (truncates decimal)
float b = (float) 5 / 2;   // b = 2.5 (not 2)
```

---

### 🔄 Pre/Post Increment & Decrement

```c
int a = 5;

// Postfix — use THEN increment
printf("%d", a++);   // prints 5, then a becomes 6

// Prefix — increment THEN use
printf("%d", ++a);   // a becomes 7, prints 7

// Decrement works same way
a--;    // postfix decrement
--a;    // prefix decrement
```

> 💡 **Interview Tip:** *"Prefix (++a): increment first, use later. Postfix (a++): use first, increment later."*

---

### 🌿 Pointers — Most Important Advanced Topic

A **pointer** is a variable that stores the **memory address** of another variable.

```c
int  a   = 10;
int *ptr = &a;   // ptr holds the ADDRESS of a
                 // & = address-of operator
                 // * = dereference operator (get value at address)

printf("%d",  a);    // 10   — value of a
printf("%p",  ptr);  // 0x... — address stored in ptr (same as &a)
printf("%d", *ptr);  // 10   — value AT the address ptr points to

// Modifying via pointer
*ptr = 20;
printf("%d", a);   // 20 — a is now changed!
```

> 💡 **Interview Tip:** *"`&` gives address. `*` dereferences (gets value at address). `int *ptr = &a` means ptr stores the address of a."*

---

### 📊 Arrays — Fixed Collection

An **array** stores multiple values of the **same data type** in **contiguous memory locations**. Index always starts at **0**.

```c
int marks[5] = {97, 88, 92, 78, 85};

// Accessing
printf("%d", marks[0]);   // 97 — first element
printf("%d", marks[4]);   // 85 — last element (index N-1)

// Array name IS a pointer to first element
int *ptr = marks;          // same as &marks[0]
printf("%d", *(ptr + 2));  // 92 — third element
```

> 💡 **Interview Tip:** *"Array index is 0 to N-1. Accessing arr[N] is out-of-bounds — undefined behavior. Array name acts as pointer to first element."*

---

### 🔤 Strings — Character Arrays

In C, a **string** is a character array terminated by a **null character `\0`**.

```c
char name[] = "Sahil";      // Automatically adds '\0' at end
// Stored as: S a h i l \0

// String functions — need #include <string.h>
strlen(str)           // Length (doesn't count '\0')
strcpy(dest, src)     // Copy string
strcat(str1, str2)    // Concatenate (append str2 to str1)
strcmp(str1, str2)    // Compare: 0=equal, +ve=str1>str2, -ve=str1<str2
strncpy(dest, src, n) // Copy first n characters
```

---

### 🏭 Functions — Reusable Code Blocks

A **function** is a block of code that performs a specific task, can be called multiple times.

```c
// 3 parts: Declaration, Definition, Call

// 1. Declaration (Prototype) — tells compiler function exists
int add(int a, int b);   // return-type name(parameter-types);

// 2. Definition — actual code
int add(int a, int b) {
    return a + b;
}

// 3. Call — use the function
int result = add(5, 10);  // 15
```

**Call by Value vs Call by Reference:**
```c
// Call by Value — original NOT changed
void doubleVal(int x) { x = x * 2; }
int a = 5;
doubleVal(a);
printf("%d", a);  // Still 5 — value copied, original safe

// Call by Reference — original IS changed
void doubleRef(int *x) { *x = *x * 2; }
doubleRef(&a);
printf("%d", a);  // Now 10 — pointer passed, original modified
```

> 💡 **Interview Tip:** *"Call by Value passes a COPY. Call by Reference passes the ADDRESS using pointers. Changes in call-by-reference affect the original variable."*

---

### 🔁 Recursion

A function that **calls itself** is recursive. Must have a **base case** to stop.

```c
int factorial(int n) {
    if (n <= 1) return 1;           // Base case — stop here
    return n * factorial(n - 1);    // Recursive call
}
// factorial(5) = 5 * 4 * 3 * 2 * 1 = 120
```

---

## 📚 Topic-by-Topic Complete Reference

---

### 📘 Chapter 1 — Variables, Data Types & Program Structure

```c
#include <stdio.h>    // Standard Input Output
#include <math.h>     // pow(), sqrt(), etc.
#include <string.h>   // strlen(), strcpy(), etc.
#include <stdlib.h>   // malloc(), free(), etc.

int main() {

    // ── VARIABLE DECLARATION ──────────────────────────────────
    int    age     = 22;
    float  pi      = 3.14;
    double salary  = 85000.50;
    char   grade   = 'A';
    char   name[]  = "SK Sahil";

    // ── OUTPUT ────────────────────────────────────────────────
    printf("Integer:  %d\n",  age);
    printf("Float:    %f\n",  pi);
    printf("Double:   %lf\n", salary);
    printf("Char:     %c\n",  grade);
    printf("String:   %s\n",  name);

    // Format specifier with precision
    printf("Pi = %.2f\n", pi);   // 3.14
    printf("Pi = %.4f\n", pi);   // 3.1400

    // Escape sequences
    printf("Tab:\tEnd\n");       // \t = tab
    printf("Newline:\nEnd\n");   // \n = newline
    printf("Backslash: \\\n");   // \\ = backslash
    printf("Quote: \"\n");       // \" = double quote

    // ── INPUT ─────────────────────────────────────────────────
    int userAge;
    printf("Enter your age: ");
    scanf("%d", &userAge);       // & = address-of operator, REQUIRED

    float weight;
    scanf("%f", &weight);        // float input

    char ch;
    scanf(" %c", &ch);           // space before %c to skip whitespace

    char city[50];
    scanf("%s", city);           // string input (no spaces)

    // ── CONSTANTS ─────────────────────────────────────────────
    const int  MAX_SIZE = 100;
    const float GRAVITY  = 9.8;

    // ── SIZEOF OPERATOR ───────────────────────────────────────
    printf("int:    %lu bytes\n", sizeof(int));     // 4
    printf("float:  %lu bytes\n", sizeof(float));   // 4
    printf("double: %lu bytes\n", sizeof(double));  // 8
    printf("char:   %lu bytes\n", sizeof(char));    // 1

    // ── VARIABLE TYPES ────────────────────────────────────────
    // Local variable — declared inside function, exists only within it
    int localVar = 10;

    return 0;
}

// Global variable — declared outside all functions, accessible everywhere
int globalVar = 100;

// Static variable — retains value between function calls
void counter() {
    static int count = 0;   // initialized only once
    count++;
    printf("Count: %d\n", count);
}
```

---

### 📘 Chapter 2 — Operators

```c
#include <stdio.h>
#include <math.h>

int main() {

    int a = 10, b = 3;

    // ── ARITHMETIC OPERATORS ──────────────────────────────────
    printf("%d\n", a + b);   // 13  — Addition
    printf("%d\n", a - b);   // 7   — Subtraction
    printf("%d\n", a * b);   // 30  — Multiplication
    printf("%d\n", a / b);   // 3   — Division (integer — truncates)
    printf("%d\n", a % b);   // 1   — Modulo (remainder)
    printf("%f\n", pow(2,10));  // 1024 — Power (use pow, not ^)

    // Division gotcha!
    printf("%d\n",   5 / 2);    // 2   — int/int = int
    printf("%f\n", 5.0 / 2);    // 2.5 — float/int = float

    // Modulo rule: sign follows dividend
    printf("%d\n",  3 % 2);   //  1
    printf("%d\n", -3 % 2);   // -1  (sign of left operand)

    // ── ASSIGNMENT OPERATORS ──────────────────────────────────
    int x = 10;
    x += 5;    printf("%d\n", x);   // 15  (x = x + 5)
    x -= 3;    printf("%d\n", x);   // 12  (x = x - 3)
    x *= 2;    printf("%d\n", x);   // 24  (x = x * 2)
    x /= 4;    printf("%d\n", x);   // 6   (x = x / 4)
    x %= 4;    printf("%d\n", x);   // 2   (x = x % 4)

    // ── RELATIONAL OPERATORS — output is 0 or 1 ───────────────
    printf("%d\n", 5 == 5);   // 1 (True)
    printf("%d\n", 5 != 5);   // 0 (False)
    printf("%d\n", 5 >  3);   // 1 (True)
    printf("%d\n", 5 <  3);   // 0 (False)
    printf("%d\n", 5 >= 5);   // 1 (True)
    printf("%d\n", 5 <= 4);   // 0 (False)

    // ── LOGICAL OPERATORS ─────────────────────────────────────
    // AND (&&) — both must be true
    printf("%d\n", (5>3) && (10>5));   // 1 (T && T = T)
    printf("%d\n", (5>3) && (10<5));   // 0 (T && F = F)

    // OR (||) — at least one must be true
    printf("%d\n", (5>3) || (10<5));   // 1 (T || F = T)
    printf("%d\n", (3>5) || (10<5));   // 0 (F || F = F)

    // NOT (!) — reverses
    printf("%d\n", !(5==5));   // 0 (!True = False)
    printf("%d\n", !(5==3));   // 1 (!False = True)

    // ── BITWISE OPERATORS ─────────────────────────────────────
    // Work on binary representation of numbers
    int p = 12;  // 1100 in binary
    int q = 10;  // 1010 in binary

    printf("%d\n", p &  q);   // 8  — AND  (1000)
    printf("%d\n", p |  q);   // 14 — OR   (1110)
    printf("%d\n", p ^  q);   // 6  — XOR  (0110) — different bits = 1
    printf("%d\n", ~p);       // -13 — NOT (inverts all bits)
    printf("%d\n", p << 1);   // 24 — Left shift (×2 per shift)
    printf("%d\n", p >> 1);   // 6  — Right shift (÷2 per shift)

    // ── INCREMENT / DECREMENT ─────────────────────────────────
    int n = 5;
    printf("%d\n", n++);  // 5 — print first, then increment (postfix)
    printf("%d\n", n);    // 6
    printf("%d\n", ++n);  // 7 — increment first, then print (prefix)
    printf("%d\n", n--);  // 7 — print first, then decrement
    printf("%d\n", --n);  // 5 — decrement first, then print

    // ── TERNARY OPERATOR (Shorthand if-else) ──────────────────
    int age2 = 20;
    char *status = (age2 >= 18) ? "Adult" : "Minor";
    printf("%s\n", status);   // Adult

    int max = (a > b) ? a : b;   // Find maximum
    printf("Max: %d\n", max);    // 10

    // ── SIZEOF OPERATOR ───────────────────────────────────────
    printf("Size of int: %lu\n", sizeof(int));

    // ── TYPE CASTING ──────────────────────────────────────────
    int   m = (int)1.999;       // Explicit — m = 1 (truncated)
    float f = (float)5 / 2;    // Explicit — f = 2.5

    return 0;
}
```

---

### 📘 Chapter 3 — Decision Control (if-else)

```c
#include <stdio.h>

int main() {

    int marks = 75;

    // ── SIMPLE IF ─────────────────────────────────────────────
    if (marks >= 40) {
        printf("Pass\n");
    }

    // ── IF-ELSE ───────────────────────────────────────────────
    if (marks >= 40) {
        printf("Pass\n");
    } else {
        printf("Fail\n");
    }

    // ── IF-ELSE IF-ELSE (Ladder) ──────────────────────────────
    if (marks >= 90) {
        printf("Grade: A\n");
    } else if (marks >= 80) {
        printf("Grade: B\n");
    } else if (marks >= 70) {
        printf("Grade: C\n");
    } else if (marks >= 60) {
        printf("Grade: D\n");
    } else {
        printf("Grade: F\n");
    }

    // ── NESTED IF ─────────────────────────────────────────────
    int age = 20;
    char citizen = 'Y';
    if (age >= 18) {
        if (citizen == 'Y') {
            printf("Eligible to vote\n");
        } else {
            printf("Not a citizen\n");
        }
    } else {
        printf("Too young to vote\n");
    }

    // ── SWITCH STATEMENT (Case Control) ───────────────────────
    int day = 3;
    switch (day) {
        case 1:
            printf("Monday\n");
            break;          // IMPORTANT: without break, falls through!
        case 2:
            printf("Tuesday\n");
            break;
        case 3:
            printf("Wednesday\n");
            break;
        case 4:
            printf("Thursday\n");
            break;
        case 5:
            printf("Friday\n");
            break;
        default:
            printf("Weekend\n");
    }

    // ── COMMON PROGRAMS ───────────────────────────────────────

    // Check even or odd
    int n = 20;
    if (n % 2 == 0) {
        printf("Even\n");
    } else {
        printf("Odd\n");
    }

    // Find largest of 3 numbers
    int x = 10, y = 30, z = 20;
    if (x >= y && x >= z) {
        printf("Largest: %d\n", x);
    } else if (y >= x && y >= z) {
        printf("Largest: %d\n", y);
    } else {
        printf("Largest: %d\n", z);
    }

    // Positive, Negative, or Zero
    int num = -5;
    if (num > 0) printf("Positive\n");
    else if (num < 0) printf("Negative\n");
    else printf("Zero\n");

    return 0;
}
```

---

### 📘 Chapter 4 — Loops (for, while, do-while)

```c
#include <stdio.h>

int main() {

    // ── FOR LOOP ──────────────────────────────────────────────
    // Syntax: for(initialization; condition; update)
    for (int i = 1; i <= 5; i++) {
        printf("%d ", i);     // 1 2 3 4 5
    }
    printf("\n");

    // Count down
    for (int i = 10; i >= 1; i--) {
        printf("%d ", i);     // 10 9 8 7 6 5 4 3 2 1
    }
    printf("\n");

    // ── WHILE LOOP ────────────────────────────────────────────
    // Use when number of iterations is NOT known beforehand
    int i = 1;
    while (i <= 5) {
        printf("%d ", i);
        i++;                  // 1 2 3 4 5
    }
    printf("\n");

    // ── DO-WHILE LOOP ─────────────────────────────────────────
    // Executes at least ONCE even if condition is false
    int k = 1;
    do {
        printf("%d ", k);
        k++;
    } while (k <= 5);         // 1 2 3 4 5
    printf("\n");

    // ── BREAK — exits the loop immediately ───────────────────
    for (int j = 1; j <= 10; j++) {
        if (j == 5) break;    // exits when j == 5
        printf("%d ", j);     // 1 2 3 4
    }
    printf("\n");

    // ── CONTINUE — skips current iteration ───────────────────
    for (int j = 1; j <= 10; j++) {
        if (j == 5) continue; // skips 5
        printf("%d ", j);     // 1 2 3 4 6 7 8 9 10
    }
    printf("\n");

    // ── NESTED LOOPS ─────────────────────────────────────────
    for (int row = 1; row <= 3; row++) {
        for (int col = 1; col <= 3; col++) {
            printf("(%d,%d) ", row, col);
        }
        printf("\n");
    }

    // ── COMMON LOOP PROGRAMS ─────────────────────────────────

    // Sum of n natural numbers (1+2+3+...+n)
    int n = 10, sum = 0;
    for (int j = 1; j <= n; j++) {
        sum += j;
    }
    printf("Sum 1 to %d = %d\n", n, sum);  // 55

    // Factorial of n
    int fact_n = 5, fact = 1;
    for (int j = 1; j <= fact_n; j++) {
        fact *= j;
    }
    printf("Factorial of %d = %d\n", fact_n, fact);  // 120

    // Multiplication table
    int table_n = 5;
    for (int j = 1; j <= 10; j++) {
        printf("%d * %d = %d\n", table_n, j, table_n * j);
    }

    // Print 1 to 100
    for (int j = 1; j <= 100; j++) {
        printf("%d ", j);
    }
    printf("\n");

    // Star pattern (right-angle triangle)
    int rows = 5;
    for (int r = 1; r <= rows; r++) {
        for (int c = 1; c <= r; c++) {
            printf("* ");
        }
        printf("\n");
    }
    // Output:
    // *
    // * *
    // * * *
    // * * * *
    // * * * * *

    // Print 1-10 except 5 (using continue)
    for (int j = 1; j <= 10; j++) {
        if (j == 5) continue;
        printf("%d ", j);
    }
    printf("\n");   // 1 2 3 4 6 7 8 9 10

    // Print 1-10 and stop at 5 (using break)
    for (int j = 1; j <= 10; j++) {
        if (j == 5) break;
        printf("%d ", j);
    }
    printf("\n");   // 1 2 3 4

    // Infinite loop (use carefully!)
    // while(1) { printf("Infinite\n"); }
    // for(;;)  { printf("Infinite\n"); }

    return 0;
}
```

---

### 📘 Chapter 5 — Functions & Recursion

```c
#include <stdio.h>

// ── FUNCTION DECLARATIONS (Prototypes) ──────────────────────────
void   printHello();
int    add(int a, int b);
float  average(float a, float b, float c);
void   swap(int *a, int *b);        // Call by Reference
int    factorial(int n);            // Recursive
int    fibonacci(int n);            // Recursive
int    maxOfTwo(int a, int b);
void   printTable(int n);

// ── FUNCTION DEFINITIONS ─────────────────────────────────────────

// No parameters, no return value
void printHello() {
    printf("Hello, World!\n");
}

// Parameters + return value
int add(int a, int b) {
    return a + b;
}

// Multiple parameters
float average(float a, float b, float c) {
    return (a + b + c) / 3.0;
}

// Call by Value — original NOT modified
void doubleValue(int x) {
    x = x * 2;   // only local copy changes
}

// Call by Reference — original IS modified (uses pointers)
void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

// Find max of two numbers
int maxOfTwo(int a, int b) {
    return (a > b) ? a : b;
}

// Print multiplication table
void printTable(int n) {
    for (int i = 1; i <= 10; i++) {
        printf("%d * %d = %d\n", n, i, n * i);
    }
}

// Recursive factorial
int factorial(int n) {
    if (n <= 1) return 1;           // Base case
    return n * factorial(n - 1);    // Recursive case
}
// factorial(5) = 5 × 4 × 3 × 2 × 1 = 120

// Recursive fibonacci
int fibonacci(int n) {
    if (n <= 0) return 0;
    if (n == 1) return 1;
    return fibonacci(n - 1) + fibonacci(n - 2);
}
// fib(0)=0, fib(1)=1, fib(2)=1, fib(3)=2, fib(4)=3, fib(5)=5

// ── MAIN ─────────────────────────────────────────────────────────
int main() {

    // Calling functions
    printHello();                          // Hello, World!
    printf("%d\n", add(5, 10));            // 15
    printf("%.2f\n", average(80, 90, 85)); // 85.00
    printf("%d\n", maxOfTwo(10, 30));      // 30

    // Call by Value — a unchanged
    int a = 5;
    doubleValue(a);
    printf("%d\n", a);    // Still 5

    // Call by Reference — values swapped
    int x = 10, y = 20;
    printf("Before: x=%d y=%d\n", x, y);  // 10 20
    swap(&x, &y);
    printf("After:  x=%d y=%d\n", x, y);  // 20 10

    // Recursion
    printf("5! = %d\n", factorial(5));     // 120
    printf("fib(7) = %d\n", fibonacci(7)); // 13

    // Print table of 5
    printTable(5);

    return 0;
}
```

---

### 📘 Chapter 6 — Arrays (1D & 2D)

```c
#include <stdio.h>

int main() {

    // ── 1D ARRAY ──────────────────────────────────────────────
    int marks[5] = {97, 88, 92, 78, 85};   // Declaration + Initialization
    int nums[5];                            // Declaration only
    int arr[] = {1, 2, 3, 4, 5};           // Size auto-determined

    // Accessing elements — index 0 to N-1
    printf("%d\n", marks[0]);   // 97
    printf("%d\n", marks[4]);   // 85

    // Modifying elements
    marks[2] = 95;

    // Input for array
    int n = 5, arr2[5];
    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i);
        scanf("%d", &arr2[i]);
    }

    // Print all elements
    for (int i = 0; i < 5; i++) {
        printf("%d ", marks[i]);
    }
    printf("\n");

    // Sum of array elements
    int sum = 0;
    for (int i = 0; i < 5; i++) {
        sum += marks[i];
    }
    printf("Sum: %d\n", sum);

    // Average
    float avg = (float)sum / 5;
    printf("Average: %.2f\n", avg);

    // Maximum element
    int max = marks[0];
    for (int i = 1; i < 5; i++) {
        if (marks[i] > max) {
            max = marks[i];
        }
    }
    printf("Max: %d\n", max);

    // Minimum element
    int min = marks[0];
    for (int i = 1; i < 5; i++) {
        if (marks[i] < min) {
            min = marks[i];
        }
    }
    printf("Min: %d\n", min);

    // Reverse an array
    int left = 0, right = 4;
    while (left < right) {
        int temp = marks[left];
        marks[left]  = marks[right];
        marks[right] = temp;
        left++;
        right--;
    }

    // Sort array (Bubble Sort)
    int size = 5;
    for (int i = 0; i < size - 1; i++) {
        for (int j = 0; j < size - 1 - i; j++) {
            if (marks[j] > marks[j + 1]) {
                int temp    = marks[j];
                marks[j]   = marks[j + 1];
                marks[j+1] = temp;
            }
        }
    }

    // ── 2D ARRAY (Matrix) ─────────────────────────────────────
    int mat[2][3] = {{1, 2, 3}, {4, 5, 6}};
    //              Row 0        Row 1
    // Access: mat[row][col]

    printf("%d\n", mat[0][0]);   // 1
    printf("%d\n", mat[1][2]);   // 6

    // Print 2D array
    for (int row = 0; row < 2; row++) {
        for (int col = 0; col < 3; col++) {
            printf("%d ", mat[row][col]);
        }
        printf("\n");
    }

    // 3x3 matrix
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    // Transpose of matrix (swap row/col)
    printf("Transpose:\n");
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d ", matrix[j][i]);   // swap i and j
        }
        printf("\n");
    }

    // ── ARRAY & POINTER RELATIONSHIP ──────────────────────────
    int data[] = {10, 20, 30, 40, 50};
    int *ptr = data;          // or: int *ptr = &data[0];

    printf("%d\n", *ptr);          // 10
    printf("%d\n", *(ptr + 1));    // 20
    printf("%d\n", *(ptr + 2));    // 30

    ptr++;
    printf("%d\n", *ptr);          // 20

    // ── PASSING ARRAY TO FUNCTION ─────────────────────────────
    // Function signature: void printArr(int arr[], int n)
    // OR:                 void printArr(int *arr, int n)
    // Call:              printArr(data, 5);

    return 0;
}
```

---

### 📘 Chapter 7 — Strings

```c
#include <stdio.h>
#include <string.h>

int main() {

    // ── STRING DECLARATION ────────────────────────────────────
    char str1[] = "Hello";           // Automatically adds '\0'
    char str2[20] = "SK Sahil";      // Fixed size
    char str3[50];                   // Empty string buffer

    // Character by character access
    printf("%c\n", str1[0]);   // H
    printf("%c\n", str1[1]);   // e
    printf("%c\n", str1[4]);   // o

    // ── STRING INPUT ──────────────────────────────────────────
    char name[50];
    printf("Enter name: ");
    scanf("%s", name);            // Reads until whitespace (no &)

    // For input with spaces use gets() or fgets()
    char fullName[100];
    fgets(fullName, 100, stdin);  // Safer: reads full line including spaces

    // ── STRING OUTPUT ─────────────────────────────────────────
    printf("%s\n", name);         // Print string
    puts(name);                   // puts() adds newline automatically

    // ── STRING FUNCTIONS (need #include <string.h>) ───────────

    char s1[50] = "Hello";
    char s2[]   = "World";

    // Length — doesn't count '\0'
    printf("Length: %lu\n", strlen(s1));      // 5

    // Copy — strcpy(destination, source)
    char dest[50];
    strcpy(dest, s1);
    printf("Copied: %s\n", dest);             // Hello

    // Concatenate — strcat(str1, str2) — appends str2 to str1
    strcat(s1, s2);
    printf("Concat: %s\n", s1);               // HelloWorld

    // Compare — strcmp(str1, str2)
    // Returns: 0 if equal, +ve if str1>str2, -ve if str1<str2
    char a[] = "abc";
    char b[] = "ABC";
    printf("Compare: %d\n", strcmp(a, b));    // Positive (lowercase > uppercase in ASCII)
    printf("Compare: %d\n", strcmp(a, a));    // 0 (equal)

    // Partial copy — strncpy(dest, src, n) — copy first n chars
    char part[10];
    strncpy(part, "Hello World", 5);
    part[5] = '\0';                           // Must add null terminator manually
    printf("Part: %s\n", part);               // Hello

    // Reverse a string manually
    char rev[] = "Hello";
    int len = strlen(rev);
    for (int i = 0; i < len / 2; i++) {
        char temp     = rev[i];
        rev[i]        = rev[len - 1 - i];
        rev[len-1-i]  = temp;
    }
    printf("Reversed: %s\n", rev);            // olleH

    // Check if string is palindrome
    char word[] = "racecar";
    int wordLen = strlen(word);
    int isPalin = 1;
    for (int i = 0; i < wordLen / 2; i++) {
        if (word[i] != word[wordLen - 1 - i]) {
            isPalin = 0;
            break;
        }
    }
    printf("%s is %s palindrome\n", word, isPalin ? "a" : "not a");

    // Count vowels
    char sentence[] = "SK Sahil is a good tutor";
    int vowelCount = 0;
    for (int i = 0; sentence[i] != '\0'; i++) {
        char c = sentence[i];
        if (c=='a'||c=='e'||c=='i'||c=='o'||c=='u'||
            c=='A'||c=='E'||c=='I'||c=='O'||c=='U') {
            vowelCount++;
        }
    }
    printf("Vowels: %d\n", vowelCount);

    // String pointer trick — print from a position
    char prog[] = "Programming";
    printf("%s\n", prog + 4);    // amming (skip first 4 chars)

    return 0;
}
```

---

### 📘 Chapter 8 — Pointers (Advanced)

```c
#include <stdio.h>

int main() {

    // ── BASIC POINTER ─────────────────────────────────────────
    int a = 10;
    int *ptr = &a;      // ptr stores address of a
                        // * in declaration = "this is a pointer"
                        // & = address-of operator

    printf("Value of a:    %d\n",  a);     // 10
    printf("Address of a:  %p\n",  &a);    // 0x7fff...
    printf("Value in ptr:  %p\n",  ptr);   // same as &a
    printf("Deref ptr:     %d\n", *ptr);   // 10 (value at address)

    // Modify via pointer
    *ptr = 20;
    printf("a is now: %d\n", a);    // 20 — original changed!

    // ── POINTER ARITHMETIC ────────────────────────────────────
    int arr[] = {10, 20, 30, 40, 50};
    int *p = arr;     // points to arr[0]

    printf("%d\n", *p);         // 10
    printf("%d\n", *(p + 1));   // 20
    printf("%d\n", *(p + 2));   // 30

    p++;                         // move to next element
    printf("%d\n", *p);         // 20

    // Traverse array with pointer
    p = arr;    // reset to start
    for (int i = 0; i < 5; i++) {
        printf("%d ", *(p + i));
    }
    printf("\n");

    // ── POINTER TO POINTER ────────────────────────────────────
    int  val = 100;
    int *ptr1 = &val;
    int **ptr2 = &ptr1;   // pointer to pointer

    printf("val  = %d\n", val);     // 100
    printf("*ptr1 = %d\n", *ptr1);  // 100
    printf("**ptr2 = %d\n", **ptr2); // 100

    **ptr2 = 200;
    printf("val now = %d\n", val);  // 200

    // ── NULL POINTER ──────────────────────────────────────────
    int *nullPtr = NULL;   // Points to nothing (safe initialization)
    if (nullPtr == NULL) {
        printf("Pointer is NULL — not pointing anywhere\n");
    }

    // ── VOID POINTER ──────────────────────────────────────────
    void *vPtr;   // Can point to any type
    int  num = 42;
    vPtr = &num;
    printf("Via void ptr: %d\n", *(int *)vPtr);  // Must cast to use

    // ── POINTER WITH FUNCTION ─────────────────────────────────
    // (see Chapter 5 — Call by Reference example)

    return 0;
}
```

---

### 📘 Chapter 9 — Advanced Topics

```c
#include <stdio.h>
#include <stdlib.h>   // for malloc, free

// ── STRUCTURES ───────────────────────────────────────────────────
struct Student {
    int   roll;
    char  name[50];
    float marks;
};

// ── TYPEDEF ──────────────────────────────────────────────────────
typedef struct Student Student;   // Now can use 'Student' instead of 'struct Student'

// Or:
typedef struct {
    int   id;
    char  dept[20];
    float salary;
} Employee;

// ── ENUM ─────────────────────────────────────────────────────────
enum Days { MON=1, TUE, WED, THU, FRI, SAT, SUN };
// MON=1, TUE=2, WED=3... (auto-increments)

// ── PREPROCESSOR DIRECTIVES ──────────────────────────────────────
#define MAX 100
#define PI  3.14159
#define SQUARE(x) ((x) * (x))   // Macro with argument

int main() {

    // ── USING STRUCT ──────────────────────────────────────────
    struct Student s1;
    s1.roll  = 101;
    strcpy(s1.name, "SK Sahil");
    s1.marks = 95.5;

    printf("Roll: %d, Name: %s, Marks: %.1f\n",
           s1.roll, s1.name, s1.marks);

    // Initialize at declaration
    struct Student s2 = {102, "Priya", 88.0};

    // Array of structs
    struct Student class[3] = {
        {1, "Ali",  90.0},
        {2, "Sara", 85.0},
        {3, "John", 78.5}
    };
    for (int i = 0; i < 3; i++) {
        printf("%d %s %.1f\n", class[i].roll, class[i].name, class[i].marks);
    }

    // Pointer to struct
    struct Student *sPtr = &s1;
    printf("Name via pointer: %s\n", sPtr->name);    // Use -> with pointer
    printf("Marks via pointer: %.1f\n", sPtr->marks);

    // ── DYNAMIC MEMORY ALLOCATION ─────────────────────────────
    int n = 5;
    int *dynArr = (int *)malloc(n * sizeof(int));   // Allocate n ints

    if (dynArr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    for (int i = 0; i < n; i++) {
        dynArr[i] = (i + 1) * 10;   // 10 20 30 40 50
    }
    for (int i = 0; i < n; i++) {
        printf("%d ", dynArr[i]);
    }
    printf("\n");

    free(dynArr);   // ALWAYS free dynamically allocated memory!
    dynArr = NULL;  // Good practice: set to NULL after freeing

    // ── ENUM USAGE ────────────────────────────────────────────
    enum Days today = WED;
    printf("Day number: %d\n", today);   // 3

    // ── MACROS ───────────────────────────────────────────────
    printf("MAX = %d\n",   MAX);          // 100
    printf("PI  = %f\n",   PI);           // 3.14159
    printf("5^2 = %d\n",   SQUARE(5));    // 25

    // ── FILE HANDLING BASICS ──────────────────────────────────
    FILE *fp;
    fp = fopen("output.txt", "w");        // Open for writing
    if (fp == NULL) {
        printf("Cannot open file\n");
        return 1;
    }
    fprintf(fp, "Hello from C!\n");       // Write to file
    fclose(fp);                            // Always close file!

    fp = fopen("output.txt", "r");        // Open for reading
    char line[100];
    while (fgets(line, 100, fp) != NULL) {
        printf("%s", line);               // Print each line
    }
    fclose(fp);

    return 0;
}
```

---

## 🧠 Complete Cheat Sheet

```c
// ════════════════════════════════════════════════════════════════
// 🏗️ STRUCTURE
// ════════════════════════════════════════════════════════════════
#include <stdio.h>
int main() { return 0; }

// ════════════════════════════════════════════════════════════════
// 📦 DATA TYPES
// ════════════════════════════════════════════════════════════════
int    x = 10;        // %d  — 4 bytes
float  y = 3.14;      // %f  — 4 bytes
double z = 3.14159;   // %lf — 8 bytes
char   c = 'A';       // %c  — 1 byte
char   s[] = "Hi";    // %s  — string (char array)
const int MAX = 100;  // constant

// ════════════════════════════════════════════════════════════════
// 📤 OUTPUT & 📥 INPUT
// ════════════════════════════════════════════════════════════════
printf("Value: %d\n", x);
printf("Float: %.2f\n", y);      // 2 decimal places
scanf("%d", &x);                  // & is REQUIRED for scalar
scanf("%s", str);                 // NO & for string/array

// ════════════════════════════════════════════════════════════════
// ➕ OPERATORS
// ════════════════════════════════════════════════════════════════
+  -  *  /  %          // Arithmetic
=  += -= *= /= %=      // Assignment
== != > < >= <=        // Relational (return 0 or 1)
&& || !                // Logical
&  | ^ ~ << >>         // Bitwise
++ --                  // Increment/Decrement
? :                    // Ternary: (cond)?trueVal:falseVal
sizeof()               // Size in bytes
(type)                 // Type casting

// Precedence: ! → */% → +- → < <= > >= → == != → && → || → =
// Associativity: Left to Right for same precedence

// ════════════════════════════════════════════════════════════════
// 🔀 CONTROL FLOW
// ════════════════════════════════════════════════════════════════
if (cond) { } else if (cond) { } else { }

switch(expr) { case val: break; default: }

// ════════════════════════════════════════════════════════════════
// 🔁 LOOPS
// ════════════════════════════════════════════════════════════════
for (int i=0; i<n; i++) { }           // known iterations
while (condition) { }                   // unknown iterations
do { } while (condition);              // at least once

break;     // exit loop
continue;  // skip to next iteration

// ════════════════════════════════════════════════════════════════
// 🏭 FUNCTIONS
// ════════════════════════════════════════════════════════════════
int add(int a, int b);                  // Declaration
int add(int a, int b) { return a+b; }  // Definition
add(5, 10);                             // Call

// Call by Value:     void fn(int x)   — original safe
// Call by Reference: void fn(int *x)  — original modified

// Recursive function (must have base case!)
int factorial(int n) {
    if (n<=1) return 1;
    return n * factorial(n-1);
}

// ════════════════════════════════════════════════════════════════
// 📊 ARRAYS
// ════════════════════════════════════════════════════════════════
int arr[5] = {1,2,3,4,5};     // 1D array
arr[0] = 10;                    // access/modify
scanf("%d", &arr[i]);           // input

int mat[2][3] = {{1,2,3},{4,5,6}};   // 2D array
mat[0][1] = 99;                        // access

// ════════════════════════════════════════════════════════════════
// 🔤 STRINGS (#include <string.h>)
// ════════════════════════════════════════════════════════════════
char s[] = "Hello";             // ends with '\0'
strlen(s)                        // length (excludes '\0')
strcpy(dest, src)               // copy
strcat(s1, s2)                  // concatenate
strcmp(s1, s2)                  // compare (0=equal)
strncpy(dest, src, n)           // copy n chars
puts(s)                         // print + newline
fgets(s, size, stdin)           // safe input with spaces

// ════════════════════════════════════════════════════════════════
// 🌿 POINTERS
// ════════════════════════════════════════════════════════════════
int a = 10;
int *ptr = &a;      // ptr stores address of a
printf("%d", *ptr); // 10 — dereference
*ptr = 20;          // changes a to 20
ptr++               // move to next memory location

int **pptr = &ptr;  // pointer to pointer
**pptr = 30;        // changes a to 30

NULL                // pointer to nothing (safe)

// ════════════════════════════════════════════════════════════════
// 🏗️ STRUCTURES
// ════════════════════════════════════════════════════════════════
struct Student { int id; char name[20]; float marks; };
struct Student s = {1, "Ali", 90.5};
s.marks = 95.0;
struct Student *p = &s;
p->marks = 95.0;    // Arrow operator with pointer

// ════════════════════════════════════════════════════════════════
// 💾 DYNAMIC MEMORY (#include <stdlib.h>)
// ════════════════════════════════════════════════════════════════
int *arr = (int *)malloc(n * sizeof(int));
free(arr);   // always free!

// ════════════════════════════════════════════════════════════════
// 📁 FILE HANDLING
// ════════════════════════════════════════════════════════════════
FILE *fp = fopen("file.txt", "w");  // r=read w=write a=append
fprintf(fp, "text");
fclose(fp);

// ════════════════════════════════════════════════════════════════
// 📋 ESCAPE SEQUENCES
// ════════════════════════════════════════════════════════════════
\n  newline    \t  tab      \r  carriage return
\\  backslash  \"  quote    \0  null character

// ════════════════════════════════════════════════════════════════
// 🗂️ FORMAT SPECIFIERS
// ════════════════════════════════════════════════════════════════
%d  int        %f  float       %lf  double
%c  char       %s  string      %p   pointer address
%lu unsigned long  %ld  long int    %o  octal  %x  hex
%.2f  2 decimal places   %5d  width 5
```

---

## 🎯 Interview Q&A — Must Know

**Q1: What is the difference between `=` and `==`?**
`=` is the assignment operator — it assigns a value. `==` is the relational operator — it compares two values and returns 1 (true) or 0 (false).

**Q2: What is a pointer? How is it different from a normal variable?**
A pointer is a variable that stores the memory address of another variable. A normal variable stores a data value; a pointer stores an address. Declared with `*`: `int *ptr = &a;`

**Q3: What is the difference between Call by Value and Call by Reference?**
Call by Value passes a copy — original is safe. Call by Reference passes the address (pointer) — original can be modified.

**Q4: What is the difference between `while` and `do-while`?**
`while` checks condition before executing — may not execute at all. `do-while` executes at least once, then checks condition.

**Q5: What does `&` do in `scanf`?**
`&` is the address-of operator. `scanf` needs the memory address of a variable to store input directly into it.

**Q6: Why is `break` important in `switch`?**
Without `break`, C falls through to the next case and executes it too (fall-through behavior). `break` exits the switch block after matching.

**Q7: What is `void` as a return type?**
`void` means the function returns nothing. Example: `void printHello() { printf("Hello"); }`

**Q8: What is the null character `\0` in strings?**
Every C string ends with `\0` (ASCII value 0), which tells the program where the string ends. `strlen()` counts characters up to but not including `\0`.

**Q9: What is the difference between `++i` and `i++`?**
`++i` (prefix) increments first, then uses the value. `i++` (postfix) uses the value first, then increments.

**Q10: What is recursion? What is mandatory for it?**
Recursion is when a function calls itself. It MUST have a base case — a condition to stop — otherwise it becomes infinite recursion and causes a stack overflow.

**Q11: What is the difference between `printf` and `scanf`?**
`printf` outputs data to the screen. `scanf` reads input from the user — requires `&` (address-of) for scalar variables.

**Q12: What is an array? Why does indexing start at 0?**
An array is a collection of same-type elements in contiguous memory. Index starts at 0 because the array name is a pointer to the first element — `arr[0]` means `*(arr + 0)`.

**Q13: What is `sizeof()` operator?**
`sizeof()` returns the size in bytes of a data type or variable at compile time. Example: `sizeof(int)` returns 4 on most systems.

**Q14: What are keywords? How many are there in C?**
Keywords are reserved words with special meaning to the compiler. There are **32 keywords** in C. You cannot use them as variable names.

**Q15: What is the difference between local, global, and static variables?**
Local: declared inside function, exists only within it. Global: declared outside all functions, accessible everywhere. Static: declared with `static`, retains its value between function calls.

---

## 🔢 MCQ Practice — Topic-wise

### Variables & Data Types

**Q1.** What is the size of `char` in C?
- A) 2 bytes  **B) 1 byte**  C) 4 bytes  D) 8 bytes

**Q2.** Which is the correct variable name?
- A) 2name  B) my name  **C) my_name**  D) my-name

**Q3.** What is the output? `int a = 1.999; printf("%d", a);`
- **A) 1**  B) 2  C) 1.999  D) Error

**Q4.** Which format specifier is used for `double`?
- A) %d  B) %f  **C) %lf**  D) %c

**Q5.** `const int MAX = 100;` — can MAX be changed later?
- A) Yes  **B) No**  C) Only inside functions  D) Depends on compiler

---

### Operators

**Q6.** What is the output? `printf("%d", 10 % 3);`
- **A) 1**  B) 3  C) 0  D) 10

**Q7.** What is `x` after `int x = 4 * 3 / 6 * 2;`?
- A) 1  B) 2  **C) 4**  D) 8

**Q8.** Which operator is used for XOR in C?
- A) `&&`  B) `||`  C) `!`  **D) `^`**

**Q9.** What is the output? `int a=5; printf("%d", a++);`
- **A) 5**  B) 6  C) 4  D) Error

**Q10.** What is the output? `int a=5; printf("%d", ++a);`
- A) 5  **B) 6**  C) 4  D) Error

**Q11.** `int a = (int)1.9; printf("%d", a);` — output?
- **A) 1**  B) 2  C) 1.9  D) Error

**Q12.** What does `5 / 2` evaluate to in C?
- A) 2.5  **B) 2**  C) 3  D) 2.0

---

### Control Flow

**Q13.** Which loop runs at least once even if condition is false?
- A) for  B) while  **C) do-while**  D) None

**Q14.** `break` inside a loop does what?
- A) Skips to next iteration  **B) Exits the loop**  C) Restarts the loop  D) None

**Q15.** `continue` inside a loop does what?
- **A) Skips to next iteration**  B) Exits the loop  C) Restarts the loop  D) None

**Q16.** What is the output?
```c
for (int i=1; i<=5; i++) {
    if (i==3) continue;
    printf("%d ", i);
}
```
- A) 1 2 3 4 5  **B) 1 2 4 5**  C) 1 2  D) 3 4 5

**Q17.** In a switch statement, what happens without `break`?
- A) Error  **B) Falls through to next case**  C) Loop repeats  D) Returns 0

---

### Arrays

**Q18.** `int arr[5] = {1,2,3,4,5}; printf("%d", arr[3]);` — output?
- A) 3  **B) 4**  C) 5  D) 1

**Q19.** `int arr[4] = {10,20,30,40}; printf("%d", arr[1]+arr[3]);` — output?
- A) 50  **B) 60**  C) 70  D) 80

**Q20.** What is the index of the last element in `int arr[5]`?
- A) 5  **B) 4**  C) 0  D) 6

**Q21.** `int arr[3]={1,2}; printf("%d", arr[2]);` — output?
- **A) 0**  B) 1  C) 2  D) Garbage

**Q22.** `int arr[2][2]={{1,2},{3,4}}; printf("%d", arr[1][0]);` — output?
- A) 1  B) 2  **C) 3**  D) 4

**Q23.** `int arr[]={1,2,3}; printf("%d", arr[2]*arr[0]);` — output?
- **A) 3**  B) 6  C) 2  D) 1

---

### Strings

**Q24.** `strcat(str1, str2)` — what does it do?
- A) Compares two strings  **B) Appends str2 to str1**  C) Copies str2 to str1  D) Returns length

**Q25.** `strlen("C Programming")` — output?
- A) 14  **B) 13**  C) 15  D) 12

**Q26.** `strcmp("abc","ABC")` — what does it return?
- A) 0  **B) Positive integer**  C) Negative integer  D) -1

**Q27.** What does every C string end with?
- A) `\t`  B) `\n`  **C) `\0`**  D) `\r`

**Q28.** `char str[]="Programming"; printf("%s", str+4);` — output?
- A) Programming  B) ogramming  **C) ramming**  D) amming

---

### Pointers

**Q29.** `int a=10; int *p=&a; printf("%d", *p);` — output?
- **A) 10**  B) Address of a  C) Garbage  D) Error

**Q30.** `int a=5; int *p=&a; *p=20; printf("%d", a);` — output?
- A) 5  **B) 20**  C) Address  D) Error

**Q31.** `int a=10; int *p=&a; int **q=&p; printf("%d", **q);` — output?
- **A) 10**  B) Address of a  C) Address of p  D) Error

**Q32.** `int arr[]={10,20,30,40}; int *p=arr; p++; printf("%d", *p);` — output?
- A) 10  **B) 20**  C) 30  D) 40

**Q33.** What does `int *ptr = NULL;` mean?
- A) ptr has value 0  **B) ptr points to nothing**  C) Error  D) ptr stores 0

---

### Functions

**Q34.** What is the output?
```c
int add(int a, int b) { return a + b; }
int main() { printf("%d", add(5,10)); }
```
- A) 5  B) 10  **C) 15**  D) Error

**Q35.** What is a function prototype?
- **A) Declaration with return type, name, parameters**  B) Function body  C) Function call  D) Return statement

**Q36.** Call by Reference uses:
- A) Normal variables  **B) Pointers**  C) Arrays only  D) Global variables

**Q37.** Recursion must have:
- A) A loop  **B) A base case**  C) Global variable  D) Two parameters

**Q38.** `factorial(5)` using recursion returns?
- A) 25  B) 60  **C) 120**  D) 24

---

## 🏆 Practice Programs — Essential Collection

### Program 1: Divisibility Check

```c
#include <stdio.h>
int main() {
    int x;
    printf("Enter a number: ");
    scanf("%d", &x);
    printf("%d", x % 2 == 0);   // 1 = Even, 0 = Odd
    return 0;
}
```

### Program 2: Average of 3 Numbers

```c
#include <stdio.h>
int main() {
    int n1, n2, n3;
    float average;
    printf("Enter three numbers: ");
    scanf("%d %d %d", &n1, &n2, &n3);
    average = (n1 + n2 + n3) / 3.0;
    printf("Average: %.2f\n", average);
    return 0;
}
```

### Program 3: Fibonacci Series

```c
#include <stdio.h>
int main() {
    int n, a = 0, b = 1, c;
    printf("Enter n: ");
    scanf("%d", &n);
    printf("%d %d ", a, b);
    for (int i = 2; i < n; i++) {
        c = a + b;
        printf("%d ", c);
        a = b;
        b = c;
    }
    printf("\n");
    return 0;
}
// 0 1 1 2 3 5 8 13 21 34...
```

### Program 4: Prime Number Check

```c
#include <stdio.h>
int main() {
    int n, isPrime = 1;
    printf("Enter a number: ");
    scanf("%d", &n);
    if (n < 2) isPrime = 0;
    for (int i = 2; i * i <= n; i++) {
        if (n % i == 0) { isPrime = 0; break; }
    }
    printf("%d is %s\n", n, isPrime ? "Prime" : "Not Prime");
    return 0;
}
```

### Program 5: Reverse a Number

```c
#include <stdio.h>
int main() {
    int n, rev = 0;
    printf("Enter number: ");
    scanf("%d", &n);
    while (n != 0) {
        rev = rev * 10 + n % 10;
        n /= 10;
    }
    printf("Reversed: %d\n", rev);
    return 0;
}
// Input: 12345 → Output: 54321
```

### Program 6: Check Palindrome Number

```c
#include <stdio.h>
int main() {
    int n, original, rev = 0;
    printf("Enter number: ");
    scanf("%d", &n);
    original = n;
    while (n != 0) {
        rev = rev * 10 + n % 10;
        n /= 10;
    }
    printf("%d is %s palindrome\n", original,
           original == rev ? "a" : "not a");
    return 0;
}
```

### Program 7: Sum of Array + Max/Min

```c
#include <stdio.h>
int main() {
    int n;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n];
    for (int i = 0; i < n; i++) {
        printf("arr[%d]: ", i);
        scanf("%d", &arr[i]);
    }
    int sum = 0, max = arr[0], min = arr[0];
    for (int i = 0; i < n; i++) {
        sum += arr[i];
        if (arr[i] > max) max = arr[i];
        if (arr[i] < min) min = arr[i];
    }
    printf("Sum: %d, Max: %d, Min: %d, Avg: %.2f\n",
           sum, max, min, (float)sum/n);
    return 0;
}
```

### Program 8: Bubble Sort

```c
#include <stdio.h>
int main() {
    int arr[] = {64, 34, 25, 12, 22};
    int n = 5;
    for (int i = 0; i < n-1; i++) {
        for (int j = 0; j < n-1-i; j++) {
            if (arr[j] > arr[j+1]) {
                int temp   = arr[j];
                arr[j]     = arr[j+1];
                arr[j+1]   = temp;
            }
        }
    }
    printf("Sorted: ");
    for (int i = 0; i < n; i++) printf("%d ", arr[i]);
    printf("\n");   // 12 22 25 34 64
    return 0;
}
```

### Program 9: String Reverse + Palindrome

```c
#include <stdio.h>
#include <string.h>
int main() {
    char str[100], rev[100];
    printf("Enter string: ");
    scanf("%s", str);
    int len = strlen(str);
    for (int i = 0; i < len; i++)
        rev[i] = str[len - 1 - i];
    rev[len] = '\0';
    printf("Reversed: %s\n", rev);
    printf("%s is %s palindrome\n", str,
           strcmp(str, rev) == 0 ? "a" : "not a");
    return 0;
}
```

### Program 10: Swap Using Pointers

```c
#include <stdio.h>
void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}
int main() {
    int x = 10, y = 20;
    printf("Before: x=%d y=%d\n", x, y);
    swap(&x, &y);
    printf("After:  x=%d y=%d\n", x, y);
    return 0;
}
// Before: x=10 y=20
// After:  x=20 y=10
```

### Program 11: Star Pattern (Triangle)

```c
#include <stdio.h>
int main() {
    int n = 5;
    // Right-angle triangle
    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= i; j++)
            printf("* ");
        printf("\n");
    }
    // Inverted triangle
    printf("---\n");
    for (int i = n; i >= 1; i--) {
        for (int j = 1; j <= i; j++)
            printf("* ");
        printf("\n");
    }
    return 0;
}
```

### Program 12: Matrix Multiplication

```c
#include <stdio.h>
int main() {
    int a[2][2] = {{1,2},{3,4}};
    int b[2][2] = {{5,6},{7,8}};
    int c[2][2] = {0};
    for (int i = 0; i < 2; i++)
        for (int j = 0; j < 2; j++)
            for (int k = 0; k < 2; k++)
                c[i][j] += a[i][k] * b[k][j];
    printf("Result:\n");
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++)
            printf("%d ", c[i][j]);
        printf("\n");
    }
    // 19 22
    // 43 50
    return 0;
}
```

### Program 13: Student Grade System (Struct)

```c
#include <stdio.h>
struct Student {
    int  roll;
    char name[50];
    int  marks;
    char grade;
};
int main() {
    struct Student s;
    printf("Enter roll, name, marks: ");
    scanf("%d %s %d", &s.roll, s.name, &s.marks);
    if      (s.marks >= 90) s.grade = 'A';
    else if (s.marks >= 80) s.grade = 'B';
    else if (s.marks >= 70) s.grade = 'C';
    else if (s.marks >= 60) s.grade = 'D';
    else                    s.grade = 'F';
    printf("\nRoll: %d | Name: %s | Marks: %d | Grade: %c\n",
           s.roll, s.name, s.marks, s.grade);
    return 0;
}
```

### Program 14: Count Words, Vowels & Digits in String

```c
#include <stdio.h>
#include <string.h>
int main() {
    char str[200];
    int vowels=0, digits=0, words=1, spaces=0;
    printf("Enter string: ");
    fgets(str, 200, stdin);
    for (int i = 0; str[i] != '\0'; i++) {
        char c = str[i];
        if (c=='a'||c=='e'||c=='i'||c=='o'||c=='u'||
            c=='A'||c=='E'||c=='I'||c=='O'||c=='U') vowels++;
        if (c>='0' && c<='9') digits++;
        if (c==' ') { spaces++; words++; }
    }
    printf("Vowels: %d | Digits: %d | Words: %d\n",
           vowels, digits, words);
    return 0;
}
```

---

## 📋 Previous Year Questions (PYQ)

These are commonly asked questions across C programming exams:

**Short Answer:**
1. What is C? Who developed it and when?
2. Differentiate between `float` and `double`.
3. What are keywords? List any 5 keywords.
4. What is the difference between `=` and `==`?
5. Explain operator precedence with an example.
6. What is the use of `break` and `continue`?
7. What is a function prototype? Why is it needed?
8. What is recursion? Give an example.
9. What is a pointer? How is it declared?
10. What is the difference between Call by Value and Call by Reference?
11. What is an array? How is it declared and initialized?
12. What is a 2D array? Give an example.
13. What is `strlen()`? What does it return?
14. What is `strcmp()`? What values can it return?
15. What is a structure? How is it different from an array?

**Programs (WAP — Write A Program):**
1. WAP to print "Hello World"
2. WAP to find sum of two numbers
3. WAP to check if a number is even or odd
4. WAP to find factorial of a number
5. WAP to print Fibonacci series up to n terms
6. WAP to check if a number is prime
7. WAP to reverse a number
8. WAP to print multiplication table
9. WAP to find sum of array elements
10. WAP to find max and min in an array
11. WAP to sort array in ascending order
12. WAP to reverse a string
13. WAP to check if a string is palindrome
14. WAP to swap two numbers using pointers
15. WAP to print a star triangle pattern

---

<div align="center">

---

**⭐ If this guide helped you, share it with your classmates! ⭐**

*Made with ❤️ by **SK SAHIL** — Freelance AI Developer & Coding Tutor*

*NYCTA — National Youth Computer Training Academy*

*Graduated from German University with Excellence Grade · Working in 4 Startups*

> *"Keep Learning · Keep Practicing · Keep Exploring · Ask your tutor whenever you face any problem!"*

---

</div>
