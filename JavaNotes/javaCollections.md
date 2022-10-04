# Collections

## ArrayList

- `ArrayList` belong to a category of classes called `collections`
- `java.util.list` extends `java.util.collections`

`ArrayList` have three constructors

- `ArrayList():` Constructs an empty list with an initial capacity of 10
- `ArrayList(Collection c):` Constructs a list containing the elements of the specified collection
- `ArrayList(int initialCapacity)` Constructs a list containing the elements of the specified collection
- `List` is an interface and cannot be instantiated.
- Use the `Arrays.asList` to  convert arrays into a list

### Methods to know for the exam

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
