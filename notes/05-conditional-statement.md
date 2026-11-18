# Conditional Statement in java

## Conditional Statements

- Conditional statements let a program make decisions by running a block of code only when a `boolean` condition is true.
- They are used to control the flow of a program, so different inputs or situations produce different behavior instead of every line running in order.
- Java has these conditional statements like `if`, `if-else`, `if-else if-else`,  `Nested-if`, `switch`

### `if` statement

- When to use
    - To run a block of code only when a condition is true, and do nothing otherwise.
- Syntax

```java
    if (condition) {
        // runs when condition is true
    }
```

- Rules
    - The condition must be a `boolean` expression.
    - Braces are optional for a single statement, but recommended.

- Caveats
    - Without braces, only the next statement belongs to the `if`.
    - A semicolon right after the condition, such as `if (x > 5);`, makes the body empty.
    - With a `boolean` variable, `if (flag = true)` compiles but assigns instead of comparing.

- Example

```java
    int age = 20;
    if (age >= 18) {
        System.out.println("Adult");
    }
```

### `if-else` statement

- When to use
    - To choose between two paths: one when the condition is true and another when it is false.

- Syntax

```java
    if (condition) {
        // runs when condition is true
    } else {
        // runs when condition is false
    }
```

- Rules
    - Exactly one of the two blocks runs.
    - `else` has no condition and must follow an `if`.

- Caveats
    - For a simple value assignment, the ternary operator is shorter.

- Example

```java
    int num = 7;
    if (num % 2 == 0) {
        System.out.println("Even");
    } else {
        System.out.println("Odd");
    }
```

### `if-else if-else` statement

- When to use
    - To choose between more than two paths based on different conditions.

- Syntax

```java
    if (condition1) {
        // runs when condition1 is true
    } else if (condition2) {
        // runs when condition2 is true
    } else {
        // runs when none are true
    }
```

- Rules
    - Conditions are checked from top to bottom, and only the first true block runs.
    - You can have any number of `else if` blocks.
    - The final `else` is optional.

- Caveats
    - Order matters: put the most specific condition first, or a broader one will catch it.
    - Too many `else if` blocks on one value are better written as a `switch`.

- Example

```java
    int score = 75;
    if (score >= 90) {
        System.out.println("A");
    } else if (score >= 60) {
        System.out.println("B");
    } else {
        System.out.println("C");
    }
```

### `Nested-if` statement

- When to use
    - When a second decision depends on the first condition being true.
- Syntax

```java
    if (condition1) {
        if (condition2) {
            // runs when both are true
        }
}
```

- Rules
    - The inner `if` is checked only if the outer condition is true.
    - Any `if` form can be nested inside another.

- Caveats
    - Deep nesting hurts readability; combine conditions with `&&` where possible.
    - Without braces, an `else` belongs to the nearest `if`.

- Example

```java
    int age = 25;
    boolean hasLicense = true;
    if (age >= 18) {
        if (hasLicense) {
            System.out.println("Can drive");
        } else {
            System.out.println("Get a license first");
        }
    }
```

### `switch` statement

- When to use
    - To compare one value against several fixed constant values.

- Syntax
```text
    // Old syntax (colon, needs break)
    switch (expression) {
        case value1:
            // code
            break;
        case value2:
            // code
            break;
        default:
            // code
    }

    // New syntax (arrow, Java 14+, no fall-through)
    switch (expression) {
        case value1 -> // code
        case value2 -> // code
        default -> // code
    }
```

- Rules
    - The expression can be `byte`, `short`, `char`, `int`, their wrapper classes, `String`, or an `enum`.
    - `long`, `float`, `double`, and `boolean` are not allowed.
    - Case values must be constants and unique.
    - `default` is optional and runs when no case matches.
    - Arrow syntax (`->`, Java 14+) does not fall through, and `switch` can also return a value as an expression.

- Caveats
    - In the old colon syntax (`case value:`), omitting `break` causes fall-through into the next case.
    - A `switch` expression must cover all possible values, usually with `default`.
    - In the old colon syntax, a missing `break` causes fall-through into the following cases, while the new arrow syntax never falls through, so `break` is not needed.

- Example

```java
int day = 3;
String name;

switch (day) {
    case 1:
        name = "Monday";
        break;
    case 2:
        name = "Tuesday";
        break;
    case 3:
        name = "Wednesday";
        break;
    default:
        name = "Other day";
}

System.out.println(name);


String name = switch (day) {
    case 1 -> "Monday";
    case 2 -> "Tuesday";
    case 3 -> "Wednesday";
    default -> "Other day";
};
System.out.println(name);
```