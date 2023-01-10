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

- ```=, <operator>=```
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

#### Precedence table

| Operator Name | Operator |  
|-----------|:-----------|
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

Mostly all operators are left associative except assignment which is right associative

```java
int a, b;
a = 2 - 3 + 4; 
/* is the same as */
b = (2 - 3) + 4;
```

Once grouped , expressions are evaluated from left to right. So in the expression ```getA()``` is invoked first.

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
    str2 == str3 // False
    ```

- (```==```) tests for the equality of references but works only for string pool strings;
- The String class has a ```.equals``` method to compare the character data of strings.

---
