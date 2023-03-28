# Basics

Some of the basics in python

## Assigning variables

- Can assign a variable to anything. (No need to specify datatype)
- Variable can be re-assigned

    ```python
    var = 1
    var = [1,2,3] 
    ```

## Data Types

Most of the basic data types in python

## `else`, `if`, `elif` logic

- Code blocks in python is done by using indentation. Anything indented below the `:` is a part of that codeblock.

    ```python
    if x < y:
        print('a')
    elif y < z:
        print('b')
    else:
        print('c')
    ```

## Loops

Loops in python

- Python uses the `for` - `in` syntax for loops

    ```python
    sq = [1,2,3]
    for a in sq:
        print(a)
    ```

- `while` is similar.

## List comprehension

Simplify common loop syntax into something/

- `for` loop example

    ```python
    x = [1,2,3,4]
    
    # Normal method
    out = []
    for num in x :
        out.append(num**2)
    
    # List Comprehension [(method) (for logic)]
    out = [num**2 for num in x]
    ```

## Functions

Function syntax for python

- All functions begin with `def` then the name of the function
- Can assign a default parameter to function parameters.
- When calling the function, can use `parameter_name=value`
- Call functions using `()`
- Use the keyword `return` to result of the function
- Documentation strings is enclosed in `""" COMMENT """`

    ```python
    """
    THIS IS A DOCSTRING....
    """
    def my_func(num1, num2 = 2):
        return num1 + num2

    output = my_func(2, num2 = 3)
    ```

## Map and Filter
