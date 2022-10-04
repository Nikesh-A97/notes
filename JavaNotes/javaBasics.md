# Java Basics

## Variables, lifespan and scope

---

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

---

## Classes

### A java source file has 3 parts

- 0 or 1 package statement
- 0 or more import statements
- 0 ore more type declarations

### Order of initialization

- static -> non static, order of initializers of variables and blocks matters

### Source file and class name

- Rule : The name of the top level public type must = name of java file
- You can have multiple classes, interfaces, enums but only 1 public
- Can have 1+ public types if nested
- Java compiler enforces the rule

---

### Imports

- Import statements are optional
- Duplicate imports and unused imports allowed
- Cannot import a sub-package, imported separately

### Main method

- Just remember psvm :
  - ``` public static void main(String[] args) ```
- Can throw exceptions
- Assume main method exists if not shown in exam
