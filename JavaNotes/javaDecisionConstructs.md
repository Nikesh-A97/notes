# Decision Constructs

## `If` - `Else` Constuct

- Just know the if-else constructs
- `else` goes with the closest `if` statement if ambiguous
- Ternary : ``` operand 1 ? operand 2 : operand 3; ```
- Must be assigned to a variable, op 2 and 3 cannot return void.
- ```?``` will only evaluate one or the other operand, not both.

---

## ```Switch``` Construct

- Looks for the matching `case` label starting from the top. If found, executes the case block then looks for `break` (if any), executing other cases below (if any).
- `break` is optional
- `default` case is optional and only 1 can exist
- switch statement evaluates `byte, char, short, int`, `enum` type and `java.lang.String`.
- `case` label type must match the type in `switch( )`
- so inside `switch ( )` you can use casts or other methods to change type
- ordering of `default` and `case` does not matter but will check `default` last if it cannot find a `case` match

---
