# 9. Handling Exceptions

## The Throwable class

- `Throwable` is the root class of all exceptions
- Contains the chain of method calls that caused the exception
- `Throwable` has two subclasses
  - `java.lang.Error`
  - `java.lang.Exception`
- `java.lang.RuntimeException` is a subclass of `java.lang.Exception`
- It's sub-classes belong to unchecked exceptions

### Throw statement

- The `throw` statement can be used to throw exceptions

### The try statement

- Consists of `try` block
- 0 or more `catch` blocks
- 0 or 1 `finally` block

    ```java
    try{
    //code
    } catch (<ExceptionClass> e){
    //code
    } finally {
    //always executes except if a sys.exit is used
    }
    ```

## Checked and Un-checked exceptions

- Compiler only checks for "checked exceptions"
- Any `exception` that extends `java.lang.throwable` but not `java.lang.RuntimeException` or `java.lang.Error` is a checked exception.
- `j.l.RE` and `j.l.Err` and their subclasses are unchecked

### Unchecked Exceptions

- There are two kinds of unchecked `exceptions` and they are exceptions that extend `j.l.RE` (runtime exceptions) and `j.l.Err` (errors).
- RuntimeException does not only imply only RuntimeExceptions can be thrown
- A well written code should not cause the JVM to throw runtime exceptions
- For `errors` the JVM itself is in danger
- `errors` include `OutOfMemoryError` or `StackOverflowError` from which no recovery is possible unlike RuntimeExceptions
- Memorize the runtime exceptions classes which are:
  - `NullPointerException`
  - `ArrayIndexOutOfBoundsException`
  - `ArithmeticException`
  - `ClassCastException`
  - `SecurityException`

### Create and invoke a method that throws an exception

- If a method can throw a `checked exception` then it must be declared in the `throws clause`.
- If it's unchecked then, then the `throws clause` is not needed.
- Can throw a subclass `exception` of the `exception` declared in the `throws clause` but not reverse
- Can use comma separated list in the `throw clause`.
- Better to declare a common superclass `exception` and throw a specific `exception`
- If an instance initializer has a `throw` statement, must declare a `throw` clause to all constructors, including the default constructor if there are none
- If a superclasses constructor has a throw clause, then the subclass most also declare the throw in it's clause

### To catch or throw & multiple catch blocks

- Can have an empty `catch` block but its better to resolve the problem
- Can have multiple `catch` statements and the control checks each catch block until it finds and resolves
- Don't put a superclass `exception` over it's subclass `exception` otherwise it becomes unreachable
- Possible to nest `try` statements
- Can re-throw `exceptions` in `catch` and `finally` blocks

### Recognize common exception classes

- Common `exceptions` that extend `RuntimeException` :
  - `ArithmeticException` - divide a number by 0
  - `ClassCastException` - fails the IS - A test
  - `IndexOutOfBoundsException` - invalid index
  - `NullPointerException` - When you try access a variable pointing to `null`
  - ---
- Common `errors` thrown by the JVM :
  - `ExceptionInInitializationError` - thrown when any `exception` is thrown while initializing a static variable or block
  - `OutOfMemoryError` - when the JVM runs out of memory
  - `StackOverflowError` - when the thread executing the method runs out of stack space, usually when a method calls itself recursively
  - ---
- Exceptions thrown by programmer (extends `RE`)
  - `IllegalArgumentException` - thrown when you determined if an argument entered is illegal
  - `NoClassDefFoundError` - thrown when it's not able to find a defn of a class
  - `NumberFormatException` - when a method that converts a `String` to a number receives a `String` that it cannot convert
  - `SecurityException` - thrown when the Security Manger refuses to permit the requested operation

- ---
