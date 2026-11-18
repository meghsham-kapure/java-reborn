# Operators in Java

Operators are special symbols that perform operations on variables and values, which are called operands.

## Arithmetic Operators

- Arithmetic operators perform basic mathematical operations on numeric operands.
    - `+`: addition, and also joins strings (concatenation).
    - `-`: subtraction.
    - `*`: multiplication.
    - `/`: division. With two integers, it gives an integer result and drops the fractional part, so `7 / 2` is `3`.
    - `%`: modulus, which gives the remainder of a division, so `7 % 2` is `1`.

## Assignment Operators

- Assignment operators assign a value to a variable.
    - `=`: assigns the right-hand value to the left-hand variable.
    - `+=`: adds the right-hand value to the variable and assigns the result, so `x += 5` is `x = x + 5`.
    - `-=`: subtracts and assigns, so `x -= 5` is `x = x - 5`.
    - `*=`: multiplies and assigns, so `x *= 5` is `x = x * 5`.
    - `/=`: divides and assigns, so `x /= 5` is `x = x / 5`.
    - `%=`: takes the remainder and assigns, so `x %= 5` is `x = x % 5`.
    - Compound operators also apply an implicit cast to the variable's type, so `byte b = 10; b += 5;` works without an error.
    
## Relational Operators

- Relational operators compare two operands and return a `boolean` result (`true` or `false`).
    - `==`: equal to.
    - `!=`: not equal to.
    - `>`: greater than.
    - `<`: less than.
    - `>=`: greater than or equal to.
    - `<=`: less than or equal to.
    - For objects, `==` compares references (memory addresses), not content. Use `.equals()` to compare content, such as with `String`.
    

## Logical Operators

- Logical operators combine or invert `boolean` expressions and return a `boolean` result.
    - `&&`: logical AND, true only if both operands are true.
    - `||`: logical OR, true if at least one operand is true.
    - `!`: logical NOT, reverses the boolean value.
    - `&&` and `||` are short-circuit operators: the right operand is not evaluated if the left operand already decides the result.

### Note 

- In Java, there are no truthy or falsy values. Only `boolean` values (`true` and `false`) can be used as conditions.
    - Relational operators work on compatible types and always return a `boolean`.
    - Numbers, strings, and objects are not automatically converted to `true` or `false`, so `if (1)` or `if ("text")` gives a compile-time error.
    - To get a boolean from another value, compare it explicitly, such as `x != 0` or `str != null`.

## Bitwise Operators

- Bitwise operators work on the individual bits of integer operands.
    - `&`: bitwise AND, gives 1 only if both bits are 1.
    - `|`: bitwise OR, gives 1 if at least one bit is 1.
    - `^`: bitwise XOR, gives 1 if the bits are different.
    - `~`: bitwise NOT, flips every bit.
    - `<<`: left shift, moves bits left and fills with 0s on the right, which multiplies by 2 for each shift.
    - `>>`: signed right shift, moves bits right and keeps the sign bit, which divides by 2 for each shift.
    - `>>>`: unsigned right shift, moves bits right and always fills with 0s.
    - `&`, `|`, and `^` also work on `boolean` operands, but unlike `&&` and `||`, they do not short-circuit.

## Unary Operators

- Unary operators work on a single operand.
    - `+`: unary plus, indicates a positive value (rarely needed).
    - `-`: unary minus, negates the value.
    - `!`: logical NOT, reverses a `boolean` value.
    - `~`: bitwise NOT, flips every bit of an integer.
    - Unary `+` and `-` promote `byte`, `short`, and `char` operands to `int`.

### Increment and Decrement Operators

- Increment and decrement operators are also unary operator used to increase or decrease a numeric variable by 1.
    - `++`: increment, adds 1 to the variable.
    - `--`: decrement, subtracts 1 from the variable.
    - Prefix (`++x`, `--x`): changes the value first, then uses the new value in the expression.
    - Postfix (`x++`, `x--`): uses the current value in the expression first, then changes it.
    - For `int x = 5;`, `int y = ++x;` gives `x = 6` and `y = 6`, while `int y = x++;` gives `x = 6` and `y = 5`.

## Ternary Operator

- The ternary operator is a shorthand for a simple `if-else` that returns a value. It is the only operator in Java that takes three operands.
    - Syntax: `condition ? valueIfTrue : valueIfFalse`.
    - The condition must be a `boolean` expression.
    - Both result expressions should be compatible types, since the whole expression produces one value.

- Use cases:
    1. Assign a value based on a condition:
        
        ```java
            int age = 20;
            String result = age >= 18 ? "Adult" : "Minor";
        ```
    
    2. Use it directly inside a print statement:

        ```java
            int num = 7;
            System.out.println(num % 2 == 0 ? "Even" : "Odd");
        ```
    
    3. Pick the larger or smaller of two values:
    
        ```java
            int a = 10, b = 25;
            int max = a > b ? a : b;
        ```
        
    4. Return a value from a method:
    
        ```java
            static String check(int marks) {
                return marks >= 40 ? "Pass" : "Fail";
            }
        ```
    
    5. Provide a default value for `null`:
    
        ```java
            String name = null;
            String display = name != null ? name : "Guest";
        ```
    
    6. Nest it for multiple conditions (avoid deep nesting, as it hurts readability):
    
        ```java
            int score = 75;
            String grade = score >= 90 ? "A" : score >= 60 ? "B" : "C";
        ```

## Type-Check Operator

- The type-check operator `instanceof` tests whether an object is an instance of a given class, subclass, or interface, and returns a `boolean`.
    - Syntax: `object instanceof Type`.
    - It returns `false` if the object is `null`.
    - The compiler gives an error if the types are unrelated.
    - Since Java 16, pattern matching lets you test and cast in one step:

    ```java
        Object obj = "Hello";

        if (obj instanceof String s) {
            System.out.println(s.length());
        }
    ```