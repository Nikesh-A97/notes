# 8. Inheritance

- Only a class can extend another class and only 1

Access modifiers on inheritance

- `private` - not inherited by the subclass
- `default` - subclass in the same package
- `protected` - same as default but subclass can be in a different package
- `public` - always inherited by the subclass
- for static variables, subclass only gets access rights to the variable not it's own copy like non-static variables.
- A subclass inherits its own copy of an instance method and can be overridden but for static method it cannot and simply gets access only

## Abstract classes and interfaces

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

### Interfaces & Abstract Classes

- An `interface` defines just the behavior and just tells you how it behaves
- An `abstract class` defines the object which drives the behavior.
- Cannot instantiate `abstract` classes or `interfaces`.

---

### Order of initialization

1. If there is a `super` class, initialize the static fields, execute static initializers in order (performed only once per class)
2. Initialize static fields and execute static initializers of the class in  order (performed only once per class)
3. If there is a super class, initialize the instance fields and execute instance initializers in order
4. Execute super class constructor
5. Initialize the instance fields and execute instance initializers of the class in order
6. Execute class constructor

---

## Overriding & Hiding

- A class can implement a method which can override an instance method in the superclass.
- It is always the instance method implemented by the class of the object that is invoked.
- static classes cannot be overridden but they can be "hidden" and both methods in the class and its super class can be accessed by casting.
- The is-a test is used to determine the relationship between two reference types, java compiler can recognise it
- Using casts can maybe fool the compiler but at run-time if it fails the is-a test then there will be a `ClassCastException`.
- Casting just changes the perspective of the object at runtime
- Does not allow to change the static/instance type of a non=private method defined in the superclass.
- Marking a method as `final` prevents subclasses from overriding the method

## Overriding methods

- The overriding method cannot be less accessible. If overridden method is `protected` the overriding method cannot be `private` however you can make it more accessible like `public`.

---
