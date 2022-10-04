# Arrays

## Declaring and initializing arrays

- One dimensional : ``` int[] ia; int ja[]; ```
- Two dimensional : ``` int[][] ib; int[] jb[]; ```
- Objects declared in the same way
- Use the ``` new ``` keyword to create an array object and must have size : ``` int[] i = new int[2]; ```
- Initial values for numeric primitives, boolean, object is ```0```, ```false```, ```null```.
- Initialize : ```int[] i = new int[]{1, 2, 3}```, cannot specify size

---

## Using Arrays

- indexing starts from 0, ends at (length - 1)
- throws my favorite ```ArrayIndexOutOfBoundsException``` if not in range
- arrays can have a length of 0
- cannot change the size of an array
- some methods on array include length and clone
- JVM enforces array type during runtime, compiler won't catch
- Covariant, store the array types' subclass.

---

## Multi-dimensional arrays

- In the example below both ```i``` and ```j``` are the same in dimensions:

 ```java
 int[][] i = new int[2][3];
 int[][] j = new int[2][];
 j[0] = new int[3];
 j[1] = new int[3];
 ```

- With this concept can create jagged arrays.

---
