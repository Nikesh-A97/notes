# Methods and Encapsulation

## Method

```java
returnType methodName(parameters){
  return matchingReturnType;
}
```

- If method numeric, return type can be a smaller return type, works with wrapper classes as well
- Return type also works if the return type is a subclass of the method return type

## varargs

- Can have multiple arguments as a parameter
- Only 1 can exist and must be the final parameter

```java
public void (int a, int... b){
  return;
}
```

---

## Overloaded methods

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

## The `static` keyword

- To access a static member or method can use the name of the class or class instance.
- Can import `static` variables and methods from classes so they can directly be used.
- Cannot access instance variables in static methods but can use an instance to access its instance variable
- a `static` initilizer in class is only executed the first time a class is loaded and initialized
- a `static` block can access all static variables and methods, variables must appear before, methods, anywhere.
- To use a static variable it must appear before the static block
- Superclass is initialized first if not done so already before the parent classes
- Cannot access/refer to the static block, only JVM can and only once

---

## Access Modifiers

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
