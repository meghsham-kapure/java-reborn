#    Looping Statements

- Looping statements run a block of code repeatedly as long as a condition holds, or for a fixed number of times.
- They are used to avoid repeating the same code and to process collections or repeat tasks until a condition changes.
- Java has these looping statements like : `for`, `for-each`, `while` , `do-while`

### `for` statement

- When to use
    - When the number of iterations is known in advance.
- Syntax

```java
for (initialization; condition; update) {
    // runs while condition is true
}
```

- Rules
    - Initialization runs once, before the first iteration.
    - The condition is checked before every iteration, and the loop stops when it is false.
    - The update runs after every iteration.
    - All three parts are optional, and `for (;;)` is an infinite loop.
    - A variable declared in the initialization is scoped to the loop only.

- Caveats
    - A semicolon right after the header, such as `for (...);`, makes the body empty.
    - Off-by-one errors are common, such as using `<=` instead of `<` with array lengths.
    - A wrong update or condition can cause an infinite loop.
    - The initialization and update parts are optional, so you can move them out of the header and use `for` like `while`, as in `for (; i <= 5;)`.

    
- Example

```java
    for (int i = 1; i <= 5; i++) {
        System.out.println(i);
    }
```

### `for-each` statement

- When to use
    - To go through every element of an array or a collection without using an index.

- Syntax

```java
    for (Type element : collection) {
        // runs once for each element
    }
```

- Rules
    - Works on arrays and any type that implements `Iterable`, such as `List` and `Set`.
    - The loop variable takes each element in order, from first to last.
    - The loop variable type must be compatible with the element type.

- Caveats
    - There is no index, so you cannot get the position of an element directly.
    - Assigning to the loop variable does not change the array or collection.
    - Adding or removing elements of a collection while looping throws `ConcurrentModificationException`.
    - It cannot go backwards or skip elements.

- Example

```java
int[] numbers = {10, 20, 30};
for (int num : numbers) {
    System.out.println(num);
}
```

### `while` statement

- When to use
    - When the number of iterations is not known in advance and depends on a condition.

- Syntax

```java
while (condition) {
    // runs while condition is true
}
```

- Rules
    - The condition is checked before every iteration, so the body may run zero times.
    - The condition must be a `boolean` expression.
    - Initialization and update must be written manually, outside the header.

- Caveats
    - Forgetting to update the variable that the condition depends on causes an infinite loop.
    - A semicolon right after the condition, such as `while (x < 5);`, makes the body empty.

- Example

```java
int i = 1;
while (i <= 5) {
    System.out.println(i);
    i++;
}
```

### `do-while` statement

- When to use
    - When the body must run at least once, such as showing a menu or asking for input before validating it.

- Syntax

```java
do {
    // runs at least once
} while (condition);
```

- Rules
    - The condition is checked after the body, so the body always runs at least once.
    - The condition must be a `boolean` expression.
    - A semicolon is required after the `while (condition)`.

- Caveats
    - Forgetting the final semicolon causes a compile-time error.
    - Forgetting to update the condition variable causes an infinite loop.

- Example

```java
int i = 1;
do {
    System.out.println(i);
    i++;
} while (i <= 5);
```