# Data Types

## Primitive data types

### Integral

- ``` byte, char, short, int, long ```

### Floating

- ``` float, double ```

### Boolean

- ``` boolean ```

### Null & Void

- ``` void ``` : method does not return anything
- ``` null ``` : valid value for a reference variable

### Primitive and Reference Variables

- Primitive var - contains the primitive data
- Reference var - stores the address of the mem location of the data
- Cannot assign address directly, only ``` null ```

---

## Declare and initialize

- Know all the ways you can initialize
- Variables can start with $ or _
- no problem if uninitialized variables as long as you don't try use them
- Java initializes static and instance variables
- Does not initialize local variables
- Can initialize local var after declaring but before being accessed
- Compiler checks if vars are initialized otherwise fails to compile

---

## Assignment

- Widening : assigning a smaller type to a large type
- Narrowing : cast required, assigning a larger type to a smaller type
- Cast needed to assign a ``` byte, short ... ``` to ``` char ``` and vice versa.

---

## The keyword ``` final ```

- A final variable is a variable that doesn't change once it has a value assigned to it
- Trying  to do so results in compilation error
- A reference variable object can be modified but cannot refer to another object

---

## The keyword ``` this ```

- Refers to instance variable
- Used when the instanced variable is shadowed
- can copy it to another variable
- cannot modify
- cannot use it inside static methods or blocks

---

## Lifecycle of an object and Garbage Collection

- An object is alive when created
- GC performed by the JVM periodically
- When theres no ref to an obj it is marked as "garbage" for GC
- Any interconnected objects and references may all be gc if one in the chain is eligible
- Basically an object can be gc if no references pointing to it

---

## Wrapper classes

- Wraps primitive data type in an object  
- Can be created using constructors that takes the relative primitive type, or string (not char).
- using the static ``` valueOf ``` method of the wrapper class
- Throws ```NumberFormatException``` if it cannot be parsed
- ``` Boolean ``` can take ``` null ``` or any string and will be set to ```false```. Passing "true" , (case insensitive) will set it to be ```true```.
- Auto - boxing : ``` Integer i = 123 ```
- ``` valueOf ``` and Auto-boxing may create cached objects (object refers to the same thing)
- Convert back using ``` <type>Value ``` method and even to other types
- unboxing but narrow casting not possible.
- ``` <wrapper>.parse<type> ``` is another method.
