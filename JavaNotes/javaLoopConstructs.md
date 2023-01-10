# Loop Constructs

## The `while` loop

- `while(expr)` loop has a control expression that will return a boolean value
- executes until expr evaluates to be false or `break` statement
- `do  while` executes body at least once

---

## The `for` loop

- Syntax: Note all sections are optional

    ```java
    for(initialization; condition; updatation){
    statement(s)
    }
    ```

- Order of execution: initialization -> condition check -> for block -> updation -> condition.
- if condition is false, `for` loop is terminated.

### Initialization

- Can have any number of expression statements and declare local variables
- Can only declare variables of one type

### Condition

- Just has an expr that returns a `boolean`, if empty then it's always `true`

### Updation

- Same as Initialization except no declarations

## Enhanced `for` loop

- Syntax:

    ```java
    for(Type variableName: array_or_Iterable){
    statement(s);
    }
    ```

## Break and Continue

- `break` will terminate the loop
- `continue` will go to the next iteration of the loop immediately
- `break` and `continue` in a nested loop terminates the loop that it's in
- Can use labels to break a specific loop that contains the loop

---
