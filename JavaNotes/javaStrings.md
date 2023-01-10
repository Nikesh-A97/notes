# Strings

## Creating Strings

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

## String methods

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

## StringBuilder class

StringBuilder class is useful for larger strings as they can be GC unlike strings from the String class

StringBuilder creation methods

```java
StringBuilder()
StringBuilder(CharSequence seq)
StringBuilder(int capacity)
StringBuilder(String str)
StringBuilder(int capacity)
```

## StringBuilder methods

### Self-reference

This mutates the current sb object

```java
reverse()
delete(int s, int e)
deleteCharAt(int indx)
replace(int s, int e, String replace) // removes the replaces
```

### Not Self-Reference

This returns a new sb object

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
