# How to Run a Java Program in VS Code

## Prerequisites

- Java (latest stable JDK)
- VS Code (with the Extension Pack for Java installed)

## Steps

1. Create a project folder, then create a file named `HelloWorld.java` inside it.

2. Write the Hello World program:

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

3. Compile and run it:

```bash
javac HelloWorld.java
java HelloWorld
```

Alternatively, run a single-file program directly without a separate compile step:

```bash
java HelloWorld.java
```

## Hello World Explained Word by Word

- `public`: access modifier that makes the class or method accessible from anywhere.
- `class`: keyword used to declare a class.
- `HelloWorld`: the class name. It must match the file name because the class is `public`.
- `static`: lets the JVM call the method without creating an object of the class.
- `void`: the method returns no value.
- `main`: the entry point method where the JVM starts running the program.
- `String[] args`: an array that holds command-line arguments passed to the program.
- `System`: a built-in class from `java.lang` that gives access to system resources.
- `out`: a static field of `System` representing the standard output stream.
- `println`: a method that prints the text and moves to a new line.
- `"Hello, World!"`: the string literal being printed.