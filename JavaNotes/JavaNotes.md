# Java Notes

Some notes made for java revision

---

### Declaration vs Definition
- Declaration : You are declaring that something exists
- Definition :  You define how something is implemented

### Compilation error vs Runtime error
- Compiler checks for syntactical errors, like package statement before everything else
- Compiler cannot identify all logical errors in the code.
- JVM throws exceptions at runtime at anything that escapes compilation

---

# 1. Java Basics
## Variables, lifespan and scope.
### Variable scope
- Visibility - class, method, block
- Lifespan - class, instance, method, loops, block
### Lifespan and scope
- When any sort of block ends (loops, methods, ...) , any variables inside cease to exist
- Compiler checks visibility only, lifetime scope affects runtime
### Scope for Exam
- Cannot define two variables with the same name and same visibility scope.
- Can overlap instance field variable with method local variable
- Cannot overlap a method scoped variable with loop/block scoped variable

## Classes
### A java source file has 3 parts
- 0 or 1 package statement
- 0 or more import statements
- 0 ore more type declarations 
### Order of initialization 
- static then non static, order of initializers of variables and blocks matters
### Source file and class name
- Rule : The name of the top level public type must = name of java file
- You can have multiple classes, interfaces, enums but only 1 public
- Can have 1+ public types if nested
- Java compiler enforces the rule
---
### Imports
- import statements are optional
- duplicate imports and unused imports allowed
- Cannot import a sub-package, imported separately 
### Main method
- Just remember psvm :
- ``` public static void main(String[] args) ``` 
- Can throw exceptions
- Assume main method exists if not shown in exam
---

# 2. Data Types

### Primitive data types

#### Integral
- ``` byte, char, short, int, long ```
#### Floating
- ``` float, double ```

#### Boolean
- ``` boolean ```

### Null & Void
- ``` void ``` : method does not return anything
- ``` null ``` : valid value for a reference variable

### Primitive and Reference Variables
- Primitive var - contains the primitive data
- Reference var - stores the address of the mem location of the data 
- Cannot assign address directly, only ``` null ```
---
### Declare and initialize
- Know all the ways you can initialize
- Variables can start with $ or _
- no problem if uninitialized variables as long as you don't try use them
- Java initializes static and instance variables
- Does not initialize local variables 
- Can initialize local var after declaring but before being accessed
- Compiler checks if vars are initialized otherwise fails to compile
---
### Assignment
- Widening : assigning a smaller type to a large type
- Narrowing : cast required, assigning a larger type to a smaller type
- Cast needed to assign a ``` byte, short ... ``` to ``` char ``` and vice versa.
---
### The keyword ``` final ```
- A final variable is a variable that doesn't change once it has a value assigned to it
- Trying  to do so results in compilation error
- A reference variable object can be modified but cannot refer to another object
---
### The keyword ``` this ```
- Refers to instance variable
- Used when the instanced variable is shadowed
- can copy it to another variable
- cannot modify
- cannot use it inside static methods or blocks
---
### Lifecycle of an object and Garbage Collection
- An object is alive when created 
- GC performed by the JVM periodically
- When theres no ref to an obj it is marked as "garbage" for GC
- Any interconnected objects and references may all be gc if one in the chain is eligible
- Basically an object can be gc if no references pointing to it
---
### Wrapper classes 
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
---

# 3. Arrays

### Declaring and initializing arrays
- One dimensional : ``` int[] ia; int ja[]; ``` 
- Two dimensional : ``` int[][] ib; int[] jb[]; ```
- Objects declared in the same way
- Use the ``` new ``` keyword to create an array object and must have size : ``` int[] i = new int[2]; ```
- Initial values for numeric primitives, boolean, object is ```0```, ```false```, ```null```.
- Initialize : ```int[] i = new int[]{1, 2, 3}```, cannot specify size
---
### Using Arrays
- indexing starts from 0, ends at (length - 1)
- throws my favorite ```ArrayIndexOutOfBoundsException``` if not in range
- arrays can have a length of 0
- cannot change the size of an array
- some methods on array include length and clone
- JVM enforces array type during runtime, compiler won't catch
- Covariant, store the array types' subclass.
### Multi-dimensional array
- In the example below both ```i``` and ```j``` are the same in dimensions:

 ```java
 int[][] i = new int[2][3];
 int[][] j = new int[2][];
 j[0] = new int[3];
 j[1] = new int[3];
 ```
- With this concept can create jagged arrays.
---

# 4. Java Operators 

## Operators
### Arithmetic 
- ``` +, - *, / % (-), ++, -- ```
### Relational 
- ``` <, <=. >, >=, ==, != ```
- for (``` ==, != ```), compares values for same numeric types and references for objects.
- for ```String``` it compares value if defined without ```new``` keyword
### Logical 
- (``` &&, || ```) short-circuiting "and" & "or. Basically evaluates the first operand and ignores second if first is irrelevant to the outcome.
- (``` &, | ```) non - short circuiting evaluates both operands
- (``` ^ ```) XOR : returns ```true``` if exactly one is ```true```
- (``` !, ? ```) negation and ternary(```if else```)
### Assignment 
- ``` =, <operator>=```
- Only works on numerics
- They are right associative 
  ```java
  int a, b, c;
  a = b = c = 10; 
  /* Is evaluated as */
  a = (b = (c = 10));
  ```
### Bitwise (not needed for exam)
- ``` &, |, ^, -, >>, <<, >>> ```
### Misc
- ``` +(str concat), .(dot), ()(cast), instanceOf, ->(lambda), [](array) ```
---
### Post/Pre Unary ```++, --```
- Post, returns existing value then evaluates
- Pre, evaluates then returns value 
- You assign the value of the expression independent of the process  of applying ```++, --```.
- For a complex expression go from L to R, example:
```java
int a = 2, b = 5;
int c = b * a * (a++ - --b) * a * b;
/*  c = 5 * 2 * (   -2    ) * 3 * 4  = -240 */
```
- Can also be applied to wrapper classes
---
### Numeric promotion and casting
- If unary operator to an operand is smaller than an ```int``` it gets promoted to one
- Example : 
```java
byte b = 1; short s = -b;
```
Will give an error to convert from ```int``` to ```short```.
- Applying an operator to numeric operands is of the same type of the larger operand but not smaller than an ```int```
- If a variable is a compile time constant then promotion is not needed.
```java
final int i = 10;
byte b = i + 2;
```
It is known during compile time that this will not overflow the byte.
- Compound assignment (```*=, +=, ...```) is implicitly cast.
- Wrapper class objects must be unboxed to their primitives before applying the operator
---
### Operator precedence and evaluation
<u>Precedence table</u>

| Operator Name | Operator |  
|-----------|:-----------:| 
| dot and array accessor | ```., []``` |   
| cast | ```()``` | 
| postfix | ```expr(++/--)```|
| unary | ```(++/--)expr, (+/-)expr, ~, !```  |
| multiplicative  | ```*, /, %``` |
| additive | ```+, -``` |
| shift | ```<, <, >, >, <<. >>, <<<, >>>``` |
| relational | ```<, <=, >, >=, =, instanceof``` |
| equality | ```==, !=``` |
| bitwise AND | ```&``` |
| bitwise exclusive OR | ```^``` |
| bitwise inclusive OR | ``` \| ``` |
| logical AND | ```&&``` |
| logical OR | ```\|\|``` |
| ternary | ``` ? : ``` |
| assignment | ```=. +=, -=, ...```  |
| $\lambda$ | ```->``` |

- Mostly all operators are left associative except assignment which is right associative
```java
int a, b;
a = 2 - 3 + 4; 
/* is the same as */
b = (2 - 3) + 4;
```
- Once grouped , expressions are evaluated from left to right. So in the expression ```getA()``` is invoked first.
```java
getA() + ( getB() + getC() )
```
---
### Equality between Strings
- Strings are immutable
- Methods that change strings just return a new string
- Without the ```new``` keyword, strings are stored in the string pool
```java
String str1 = "test";
String str2 = "test";
String str3 = new String("test");
str1 == str2 // True
str1 == str3 // False
str4 == str3 // False
```
- (```==```) tests for the equality of references but works only for string pool strings;
- The String class has a ```.equals``` method to compare the character data of strings.
---
# 5. Decision Constructs
### If-Else
- Just know the if-else constructs
- else goes with the closest if statement if ambiguous
- Ternary : ``` operand 1 ? operand 2 : operand 3; ```
- Must be assigned to a variable, op 2 and 3 cannot return void.
- ```?``` will only evaluate one or the other operand, not both.
---
### Switch statement
- Looks for the matching `case` label starting from the top. If found, executes the case block then looks for `break` (if any), executing other cases below (if any).
- `break` is optional
- `default` case is optional and only 1 can exist
- switch statement evaluates `byte, char, short, int`, `enum` type and `java.lang.String`.
- `case` label type must match the type in `switch( )`
- so inside `switch ( )` you can use casts or other methods to change type
-  ordering of `default` and `case` does not matter but will check `default` last if it cannot find a `case` match
---
# 6. Loop Constructs
### The `while` loop
- `while(expr)` loop has a control expression that will return a boolean value
- executes until expr evaluates to be false or `break` statement
- `do  while` executes body at least once
---
### The `for` loop
- Syntax: Note all sections are optional 
```java
for(initialization; condition; updating){
  statement(s)
}
``` 
- Order of execution: initialization -> condition check -> for block -> updation -> condition.
- if condition is false, `for` loop is terminated.
 
 Initialization 
- can have any number of expression statements and declare local variables
- Can only declare variables of one type

Condition:
- just has an expr that returns a `boolean`, if empty then it's always `true`

Updation:
- Same as Initialization except no declarations

### Enhanced `for` loop
- Syntax:
```java
for(Type variableName: array_orIterable){
  statement(s);
}
```
### Break and Continue
- `break` will terminate the loop
- `continue` will go to the next iteration of the loop immediately
- `break` and `continue` in a nested loop terminates the loop that it's in
- Can use labels to break a specific loop that contains the loop

---
# 7. Methods and Encapsulation
### Method:
```java
returnType methodName(parameters){
  return matchingReturnType;
}
```
- If method numeric, return type can be a smaller return type, works with wrapper classes as well
- Return type also works if the return type is a subclass of the method return type

### varargs
 - Can have multiple arguments as a parameter
 - Only 1 can exist and must be the final parameter
```java
public void (int a, int... b){
  return;
}
```
---
### Overloaded methods
- Method signature consists of the method name and the ordered list of parameter types
- The example below shows that they are both different
```java
public void methodA(int a, long b){}
public void methodA(long a, int b){}
```
### Method selection rules
1. If method signature is different then it matches that first
2. Finds the exact match first, applies to primitives as well
3. If no exact match then the most similar or close to the type being passed is matched
4. Priority is given to the primitive if it can be widened after autoboxing
5. If an argument can be autoboxed into a method parameter type then the one without varargs is considered.

---
### The `static` keyword
- To access a static member or method can use the name of the class or class instance.
- Can import `static` variables and methods from classes so they can directly be used.
- Cannot access instance variables in static methods but can use an instance to access its instance variable
- a `static` initilizer in class is only executed the first time a class is loaded and initialized
- a `static` block can access all static variables and methods, variables must appear before, methods, anywhere.
- To use a static variable it must appear before the static block
- Superclass is initialized first if not done so already before the parent classes
- Cannot access/refer to the static block, only JVM can and only once
---
### Access Modifiers
- The accessibility modifiers are `private, protected, public` and if there is none then it's `default`
- `private` - can only be accessed from within the class and nowhere else
- `default` - accessible to all classes in the same package.
- `protected` - accessible to all classes in the same package and subclass irrespective of the package
- `public` accessible from anywhere
- `private > default > protected > public`
- `protected` allows a subclass to access its own fields that the subclass inherits from its superclass

### Applying modifiers to types
- A top level class, interface or enum can only have `public` or `default`.
- Nested classes, interfaces or enums can use all 4
- In an interface, variables and methods are always `public`
- In an enum, enum constants are `public`, constructors are `private`, fields and methods can be any
---
### Creating and overloading constructors
- Can have instance blocks that execute when the class is initialized and these blocks an access all the members of the class
- forward referencing
```java
public class TestClass{
  {
    System.out.print(i); // invalid
    i = 20; // valid
    print(); //valid
  }
  void print(){ System.out.print(i); }
  int i = 10;
  ...
}
```
- constructors have the same name as the class and no return types including void
- If no constructor, the compiler auto adds a constructor in the form of `ClassName(){}`
- If there is one, then it won't add the default constructor
- Similar to overloading methods, you can overload constructors as long as they have a different signature
- Can invoke other constructors using `this()` but must be the first line and so can only call one constructor at most
- You can chain multiple constructors
- When creating an instance of a class, JVM executes all of the instance initializers first then the constructor
- A static final variable can only be used after the class is initialized explicitly ( through initializers) or implicitly
---
### Encapsulation
- Encapsulate class by keeping class variables private
- Use getters and setters to change variables
- Use proper naming conventions
### Passing object references and primitive values in methods
- Java uses pass by value
- You only pass the value to the method or address of the object of where it is stored
---
# 8. Inheritance
- Only a class and extend another class and only 1

Access modifiers on inheritance
 - `private` - not inherited by the subclass
 - `default` - subclass in the same package
 - `protected` - same as default but subclass can be in a different package
 - `public` - always inherited by the subclass
 - for static variables, subclass only gets access rights to the variable not it's own copy like non-static variables.
 - A subclass inherits its own copy of an instance method and can be overridden but for static method it cannot and simply gets access only

### Abstract classes and interfaces
- An `abstract class` doesn't have to have an abstract method.
- Concrete classes cannot have `abstract` methods.
- An `abstract class` cannot be instantiated
- A `final class` or `final` method cannot be `abstract`
- A `final class` cannot contain an `abstract` method
- An `abstract class` can contain a `final` method
- A `private` method is always `final`
- A `private` method can never be `abstract`
- A `static` method can be `final` but never `abstract`
- Conventionally the sequence of modifiers in a method declaration is
```java
<access modifier><static><final or abstract><returnType>methodName(<parameter list>){}

public static final void main(String[] args){}
```
---
### Interfaces
- Everything in an `interface` is implicitly public
- Cannot declare as `private` or `protected`
- An interface is implicitly `abstract`
- All variables defined in an interface are implicitly `public static final`
- Avoid creating variables in an interface
- An interface can have
  - `abstract` methods, the keyword is optional
  - `default` methods, must have a body and declare method `default` if it has a body
  - `static` methods belongs to the interface itself
- A class can extend only 1 `class` and implement multiple `interfaces`
- `static` methods cannot be inherited 
- If there are two `default` methods with the same name from different interfaces, code will not compile until the class provides an implementation
- It is possible for an interface to `extend` any number of `interfaces`
---
Cannot instantiate `abstract` classes or `interfaces`.

### Difference between an Interface and an Abstract Class
An `interface` defines just the behavior and just tells you how it behaves
An `abstract class` defines the object which drives the behavior.

---
### Order of initialization
1. If there is a `super` class, initialize the static fields, execute static initializers in order (performed only once per class)
2. Initialize static fields and execute static initializers of the class in  order (performed only once per class)
3. If there is a super class, initialize the instance fields and execute instance initializers in order
4. Execute super class constructor
5. Initialize the instance fields and execute instance initializers of the class in order
6. Execute class constructor

---

# 9. Handling Exceptions

### The Throwable class
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
   -  `NullPointerException`
   -  `ArrayIndexOutOfBoundsException`
   -  `ArithmeticException`
   -  `ClassCastException`
   -  `SecurityException`

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

---
# 10 Inheritance

Classes are polymorphic, so if class B extends class A, then class B behaves as both class A and B but class A only behaves like class A.

Only  non-private instance methods can be overridden. Static methods and variables can just be hidden.

## Overriding & Hiding
- A class can implement a method which can override an instance method in the superclass.
- It is always the instance method implemented by the class of the object that is invoked.
- static classes cannot be overridden but they can be "hidden" and both methods in the class and its super class can be accessed by casting.
- The is-a test is used to determine the relationship between two reference types, java compiler can recognise it
- Using casts can maybe fool the compiler but at run-time if it fails the is-a test then there will be a `ClassCastException`.
- Casting just changes the perspective of the object at runtime
- Does not allow to change the static/instance type of a non=private method defined in the superclass.
- Marking a method as `final` prevents subclasses from overriding the method
### Overriding methods
#### <u>Accessibility</u>
- The overriding method cannot be less accessible. If overridden method is `protected` the overriding method cannot be `private` however you can make it more accessible like `public`.

### <u>Return Type</u>
- The return type of the overriding method must be the same or a sub type of the overridden method. This a called a covariant return.

### <u>Parameters</u>
- The list of parameters in the overriding method must match exactly ot return type of the overridden method.

### <u>Throws Clause</u>
- The overriding method cannot have a wider exception.
---
# 11. Selected classes from the Java API

## Strings
### Creating Strings
Ways to construct strings
```Java
String()
String(String str)
String(byte[] bytes)
String(char[] value)
```
- Can create strings through concatenation
- Evaluated from left to right
- Can override the `toString()` method
- Strings are immutable any `String` methods that change the string actually just return a new string

### String methods
```java
int length() //length
char charAt(int index) // char value
int indexOf(int ch) // index or -1
// Starting is inclusive, ending is exclusive
String subString(int sIndx, int eIndx) 
String subString(int sIndx)
String concat(String str)
String to(Lower/Upper)Case()
String replace(char oldChar, char newChar)
String trim() // trims white spaces from both ends
/* ===== */
boolean startsWith(String pre)
boolean endsWith(String suff)
boolean contains(CharSequence s)
boolean equals(Object obj)
boolean equalsIgnoreCase(String anotherString)
boolean isEmpty()
```

### StringBuilder class
StringBuilder class is useful for larger strings as they can be GC unlike strings from the String class

StringBuilder creation methods
```java
StringBuilder()
StringBuilder(CharSequence seq)
StringBuilder(int capacity)
StringBuilder(String str)
StringBuilder(int capacity)
```

String builder methods
- Self-ref (mutates the current sb object)
```java
reverse()
delete(int s, int e)
deleteCharAt(int indx)
replace(int s, int e, String replace) // removes the replaces
```
- not self-ref and other (returns a new sb)
```java
int capacity()
char charAt(int indx)
int length()
int indexOf(String str)
int indexOf(String str, int sIndx)
void setLength(int len) // truncates if length < existing str.len
String substring(int s)
String substring(int s int e)
String toString()
```
---

## Calendar data
The `java.time` package is the main package of the date/time framework.
The machine view of time is the number of milliseconds that have elapsed since the Epoch.
- Based on the ISO calender system
- All classes are `immutable` and `thread` safe
- Clear seperation between machine and human view of time

The following are the different types
- `Instant`: Represents the machine view of time
- `LocalDate/LocalTime/LocalDateTime/ZonedDateTime` represent human view of time.
- Use specific types to capture different components
- `Period` represents a date in terms of Days Months and Years only
- `Duration` represents the time-based amount of time in terms of Hours Minutes and Seconds
- Can use `enums` `Month` and `DayOfWeek`
- Various methods 

`#todo`

---
## ArrayList
- `ArrayList` belong to a category of classes called `collections`
- `java.util.list` extends `java.util.collections`

`ArrayList` have three constructors
- `ArrayList():` Constructs an empty list with an initial capacity of 10
- `ArrayList(Collection c):` Constructs a list containing the elements of the specified collection
- `ArrayList(int initialCapacity)` Constructs a list containing the elements of the specified collection

- `List` is an interface and cannot be instantiated.
- Use the `Arrays.asList` to  convert arrays into a list

Methods to know for the exam
- `String toString();`
- `boolean add(E e)` returns true or false, adds on the end of list
- `void add (int index, E element)` inserts at exact position
- `boolean addAll(Collection<? extends  E> c)` add a list into another list
- `boolean addAll(int indx, Collection<? extends  E> c)`
- `E remove(int index)` returns the removed value
- `boolean remove(Object o)` removes the first instance of the object `o` it  finds
- `boolean removeAll(Collection <?>c)` removes all occurrences of an element
- `void clear()` removes all elements from this list
- `E set(int indx, E element)` replaces the element at the specified indx, returns element replaced
- `boolean contains(Object o)` returns `true` as soon as match is found
- `E get(int indx)` - self explantory
- `int indexOf(Object o)` use the equals method, returns -1 if not found
- `boolean isEmpty()`
- `int size()`
- `List<E>subList(int fromIndex, int toIndex)` a view of the original list, any changes made to the sub-list is made to the original list

Some important notes on `ArrayList`
- Adding nulls
- Adding duplicates
- Only throws `IndexOutOfBoundsException`
- Cannot method chain like `StringBuilder`
---

## Lambda Expressions

### Writing Lambda expressions

### Using predicate interface

### Calender Data
- All classes are immutable and thread-safe
- `Instant` - number of miliseconds since the epoch
- `Local<Date/Time/DateTime>` and `ZoneDateTime` represent human view of time
- `Period` a date-based amount of time in terms of Days, Months and Years
- `Duration` represents time based in terms of Hours, Minutes and Seconds
- NO date/time classes have a constructor.
### of-methods
```java
static LocalDate of(int year, ,<int/Month month>, int dayOfMonth)
```
```java
static LocalTime of(int hour, int minute (int second (int nanoOfSecond)))
```

```java
static LocalDateTime of(LocalDate date, LocalTime time)
```
- Indexing for month starts from 1, hours start from 0-23
- Throws `DateTimeException` (unchecked)
- 