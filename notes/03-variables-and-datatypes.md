# Variables and Datatype

## Identifier, Keyword, and Literal

- Identifier: a name you give to a class, method, variable, or other element, such as `HelloWorld`, `main`, or `args`.

- Keyword: a reserved word with a fixed meaning in Java that cannot be used as an identifier, such as `public`, `class`, `static`, or `void`.
    - Java has 68 keywords in total.
    - 51 are reserved keywords, which can never be used as identifiers.
    - 17 are contextual keywords, such as `var`, `record`, `sealed`, `yield`, `permits`, and `when`, which are only treated as keywords in specific contexts.
    - 2 reserved keywords are unused: `const` and `goto`.
- Literal: a fixed value written directly in the code, such as `"Hello, World!"`, `10`, `3.14`, `'A'`, or `true`.
    - `true`, `false`, and `null` are literals, not keywords.
    - You can store literals in constant variables.

## Variables and Datatype

- Variables are:
    - a named memory location.
    - named using an identifier.
    - acts as container that stores data.
    - a reference through which we can read the value or write a new one.

- Datatype is:
    - the named type of data a variable holds.
    - a label on the container that identifies the type of value it can store.
    - a restriction: the label allows the container to store only values that match its type.
    - fixed in Java: the datatype of a variable cannot be changed once declared.


## Rules and Conventions around Variables and Datatype

- Rules:
    - A variable name can contain letters, digits, underscore `_`, and dollar sign `$`.
    - It cannot start with a digit.
    - It cannot be a keyword, and a single `_` alone is not allowed.
    - It cannot contain spaces or other special characters.
    - It is case-sensitive: `age` and `Age` are different variables.
    - A variable must be declared with a datatype before it is used.
    - A local variable must be initialized before it is read.

- Conventions:
    - Use camelCase for variable names, such as `studentName` which start with a lowercase letter.
    - Use meaningful names instead of single letters, except for short loop counters like `i`.
    - Write constants in UPPER_SNAKE_CASE with the `final` keyword, such as `MAX_SIZE`.
    - Avoid starting names with `$` or `_`.

## Syntax and example

```text
Declaration 
datatype variableIdentifier ;

Definition
variableIdentifier = value ;

Declaration and Definition
datatype variableIdentifier = value ;

```

## What is a statically typed language?

A statically typed language is one where the datatype of every variable is known and checked at compile time, before the program runs. In Java, you must declare the type of a variable, and the compiler reports an error if you assign a value of a different type.

## Types of Data Types

## Primitive Data Types
    - Built-in data types predefined by Java that store simple values directly in memory.
    - They have a fixed size, hold no methods, and cannot be `null`.
    - Java has 8: `byte`, `short`, `int`, `long`, `float`, `double`, `char`, and `boolean`.

### Integers ( whole numbers with no fractional part )

1. `byte`
    - Description: the smallest integer type, storing whole numbers.
    - Usage: small whole numbers to save memory, such as in large arrays.
    - Size: 1 byte (8 bits).
    - Range: -128 to 127.
    - Default value: `0`.

2. `short`
    - Description: a small integer type, storing whole numbers.
    - Usage: small whole numbers where `int` is not needed.
    - Size: 2 bytes (16 bits).
    - Range: -32,768 to 32,767.
    - Default value: `0`.

3. `int`
    - Description: the standard integer type, storing whole numbers.
    - Usage: the most common choice for whole numbers.
    - Size: 4 bytes (32 bits).
    - Range: -2,147,483,648 to 2,147,483,647.
    - Default value: `0`.

4. `long`
    - Description: a large integer type, storing whole numbers.
    - Usage: very large whole numbers beyond the `int` range.
    - Size: 8 bytes (64 bits).
    - Range: -2^63 to 2^63 - 1.
    - Rule: ends with `L`
    - Default value: `0L`.

 > Any integer value that is out of range gets wrapped around. For example, `(byte) 262` becomes `6`, because 262 - 256 = 6.
 
### Real Numbers ( real numbers can have a fractional (decimal) part )

1. `float`
    - Description: a single-precision decimal type.
    - Usage: decimal numbers where about 6 to 7 digits of precision is enough.
    - Size: 4 bytes (32 bits).
    - Range: approximately ±3.4 × 10^38.
    - Rule: ends with `f`
    - Default value: `0.0f`.
2. `double`
    - Description: a double-precision decimal type.
    - Usage: the default choice for decimal numbers, with about 15 to 16 digits of precision.
    - Size: 8 bytes (64 bits).
    - Range: approximately ±1.7 × 10^308.
    - Rule: ends with `d`
    - Default value: `0.0d`.


### Characters ( can be alphabetic, special symbols or number values)

1. `char`
    - Description: stores a single 16-bit Unicode character.
    - Usage: single characters such as letters, digits, or symbols.
    - Size: 2 bytes (16 bits).
    - Range: 0 to 65,535 (`'\u0000'` to `'\uffff'`).
    - Rule: always enclosed in single quotes
    - Default value: `'\u0000'`.

### Booleans (binary value `true/false ,1/0 `)

1. `boolean`
    - Description: stores a logical value.
    - Usage: true or false values, such as conditions and flags.
    - Size: not precisely defined by the Java specification; it depends on the JVM (commonly 1 byte).
    - Range: `true` or `false`.
    - Default value: `false`.

## Non-Primitive Data Types

    - Data types that are not predefined as simple values; they are created by the programmer or provided by Java as classes, and they store a reference (memory address) to an object.
    - They can have methods and can be `null`.
    - Examples: `String`, arrays, classes, interfaces, and enums.